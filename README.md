This AWS Lambda function automates the process of restoring objects stored in Glacier or Deep Archive storage classes and moves them to the Standard storage class.

**Features**
Scans a specified S3 URI to identify objects in Glacier or Deep Archive.
Initiates the restore process for 28 days using the Standard retrieval tier.
Skips files that are already restored or in the process of being restored.
Handles errors gracefully to ensure the script continues processing other objects.

**Usage**
Update the s3_uri in the Lambda function with your desired S3 path (e.g., s3://bucket-name/folder-path/).
Deploy the Lambda function in AWS.
Trigger the Lambda function to begin restoring objects.

**Prerequisites**
AWS account with proper permissions for:
s3:ListBucket
s3:GetObject
s3:RestoreObject
Python environment with the boto3 library.

**Example Output**
Successfully restored: file1.txt
Skipped (already restoring): file2.txt
Already restored: file3.txt
