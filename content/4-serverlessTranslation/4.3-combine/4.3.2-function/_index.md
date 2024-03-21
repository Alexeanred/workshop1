---
title : "Configure Combine function"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 4.3.2 </b> "
---

1. In combine function:
   + In the **Code** section:
     + Enter the following code:
    ```python
    import boto3
    import json
    import os

    s3 = boto3.client('s3')

    def combine_content(files):
        # Combine the content of multiple files
        combined_content = ''
        for file_content in files:
            combined_content += file_content + "\n\n"
        return combined_content

    def group_keys_by_pattern(key_names, pattern):
        grouped_keys = {pattern: []}

        for key_name in key_names:
            if pattern in key_name:
                grouped_keys[pattern].append(key_name)

        return grouped_keys

    def sample_event_func(input_key_name):
        # Initialize the S3 client
        s3 = boto3.client('s3')

        # If key_names is not provided, retrieve key names from the bucket
        # Specify the bucket name
        bucket_name = os.environ.get('OutputBucket')

        try:
            # List objects within the bucket
            response = s3.list_objects_v2(Bucket=bucket_name)

            # Extract key names from the response
            if 'Contents' in response:
                key_names = [obj['Key'] for obj in response['Contents']]
                print(key_names)
            else:
                print("No objects found in the bucket.")
                return
        except Exception as e:
            print(f"Error: {e}")
            return

        # Extract pattern from the input key name
        parts = input_key_name.rsplit("-", 1)
        print(parts)
        if len(parts) > 1 and parts[1].rsplit(".", 1)[0].isdigit():  # Check if the part on the right is not a number
            pattern = parts[0]  # Use the part on the left as pattern
        else:
            pattern = input_key_name  # Use the entire input_key_name as pattern
        print(pattern)
        # Group key names based on the extracted pattern
        grouped_keys = group_keys_by_pattern(key_names, pattern)
        print(grouped_keys)
        # Create sample event containing keys with similar pattern
        sample_event = {
            "Records": [
                {
                    "s3": {
                        "bucket": {
                            "name": os.environ.get('OutputBucket')
                        },
                        "object": {
                            "key": key_name
                        }
                    }
                } for key_name in grouped_keys[pattern]
            ]
        }

        return sample_event
        
    def lambda_handler(event, context):
        # Specify the bucket name
        bucket_name = os.environ.get('OutputBucket')
        print(event)
        # List to store the content of all files
        key_name = event['Records'][0]['s3']['object']['key']
        print(key_name)
        file_contents = []
        files_to_delete = []
        sample_events = sample_event_func(key_name)
        # Check if sample_events is empty
        if not sample_events:
            return {
            'statusCode': 205,
            'body': 'File not found in the bucket'
        }
        if not sample_events['Records']:
            print("No sample events generated.")
            return {
            'statusCode': 206,
            'body': 'Exit the lambda_handler because the records has been handled'
        }
        print(sample_events)
        # Loop through each record in the event
        for record in sample_events['Records']:
            print(record)
            # # Extract the bucket and file key from the record
            bucket = record['s3']['bucket']['name']
            key = record['s3']['object']['key']
            # tan dung bucket de lay key name
            # Retrieve the content of the file
            file_obj = s3.get_object(Bucket=bucket, Key=key)
            
            # Extract the content from the file object
            file_content = file_obj['Body'].read().decode('utf-8')
            print(file_content)
            
            file_contents.append(file_content)
            
            # Append the content to the combined content
            # combined_content += file_content + "\n\n"
            # print("Day la combine lan ",count)
            # print(combined_content)
            files_to_delete.append({'Key': key, 'Bucket': bucket})
            print(files_to_delete)
            # count+=1
        print(file_contents)
        # # Write the combined content to a new file
        combined_content = combine_content(file_contents)
        print("Key hien tai la: ", key)
        copy_k = key
        parts = copy_k.rsplit("-", 1)
        print(parts)
        if len(parts) > 1 and parts[1].rsplit(".", 1)[0].isdigit():  # Check if the part on the right is not a number
            combined_key = parts[0] + ".txt" # Use the part on the left as pattern
        else:
            combined_key = copy_k  # Use the entire input_key_name as pattern
        #combined_key= "new_ielst.txt"
        print("Key sau khi chinh sua la: ", combined_key)
        s3.put_object(Bucket=os.environ.get('NewBucket'), Key=combined_key, Body=combined_content.encode('utf-8'))
        # Delete the original files
        print("Files of delete: ",files_to_delete)
        for file_to_delete in files_to_delete:
            print(file_to_delete)
            s3.delete_object(Bucket=file_to_delete['Bucket'], Key=file_to_delete['Key'])
            print("Deleted file ",file_to_delete['Key'])
            
        return {
            'statusCode': 200,
            'body': 'Files combined successfully!'
        }

    # Entry point for local testing
    if __name__ == '__main__':
        sample_event = {
            "Records": [
                {
                    "s3": {
                        "bucket": {
                            "name": "example-bucket"
                        },
                        "object": {
                            "key": "example.txt"
                        }
                    }
                },
                {
                    "s3": {
                        "bucket": {
                            "name": "example-bucket"
                        },
                        "object": {
                            "key": "example1.txt"
                        }
                    }
                }
            ]
        }
        lambda_handler(sample_event, None)
    ```

    + Explanation:
        + We will reconfigure events with a function to receive the name of the event's object.
        + Then, the function will look for characteristics to find files with the same format to create an event containing the names of those objects and combine them.
        + Thus, when translating multiple documents at once, there will be no error of not being able to find the correct files to combine.
    + Then, select the **Deploy** button to have the function update to the latest code.
![combinefunc](/images/4.s3/004-combine.png)

2. Then, go to **Configuration**:
   + Select **Environment variables**.
   + Select the **Edit** button.
![combinefunc](/images/4.s3/005-combine.png)
3. In Environment variables:
   + Select the button: **Add environment variable**.
   + In **Key**: enter ```OutputBucket```.
   + In **Value**: enter ```translated-bucket-<your_id>```.
   + Select the button: **Add environment variable**.
   + In **Key**: enter ```NewBucket```.
   + In **Value**: enter ```final-translated-bucket-<your_id>```.
   + Select the **Save** button.
![combinefunc](/images/4.s3/006-combine.png)
5. You can access cloudwatch to view the log of the request we sent:
   + Select **Monitor**.
   + Select **View Cloudwatch logs**.
![combinefunc](/images/4.s3/007-combine.png)
6. Select **log streams** to view the log and refresh if there is a new log sent in.
![combinefunc](/images/4.s3/008-combine.png)

**Hooray!!! You have finished configuring the combine function.**
