## FunctionDef upload_to_s3(local_file, bucket, s3_file)
**upload_to_s3**: The function of upload_to_s3 is to upload a file to an Amazon S3 bucket using the provided credentials.

**parameters**:
- local_file: The path to the local file that needs to be uploaded.
- bucket: The name of the S3 bucket where the file will be uploaded.
- s3_file: The name of the file in the S3 bucket.

**Code Description**:
The upload_to_s3 function utilizes the boto3 library to create an S3 client with the specified AWS access key and secret key. It then attempts to upload the local file to the designated S3 bucket with the given file name. If the upload is successful, it prints "Upload Successful" and returns True. If the local file is not found, it catches a FileNotFoundError and prints "The file was not found," returning False. In case of missing credentials, it catches a NoCredentialsError, prints "Credentials not available," and returns False.

**Note**:
- Ensure that the AWS access key and secret key provided have the necessary permissions to upload files to the specified S3 bucket.
- Handle exceptions appropriately when calling this function to manage file upload errors.

**Output Example**:
True
