# Lambda-S3-Assignment2_12
Lambda-S3-Assignment
1. What is the purpose of the execution role on the Lambda function? 
The execution role allows the Lambda function to interact with AWS resources. It defines what actions the Lambda function can perform and on which resources. For example, it may include permissions to read files from the S3 bucket, write logs to CloudWatch, or upload files to an S3 bucket.

2. What is the purpose of the resource-based policy on the Lambda function?
A resource-based policy on the Lambda function allows external AWS resources or services to invoke the Lambda function. For example, an S3 bucket triggering the Lambda function when a file is created requires a resource-based policy granting the S3 bucket permissions to invoke the Lambda.

 3. If the function is needed to upload a file into an S3 bucket, describe (i.e no need for the actual policies) –
 What is the needed update on the execution role? - What is the new resource-based policy that needs to be added? To which resource?
Update on the Execution Role:
Add permissions to the execution role to allow the Lambda function to perform actions like s3:PutObject and s3:PutObjectAcl on the specific S3 bucket where the file will be uploaded.

New Resource-Based Policy:
Add a policy to the S3 bucket's resource-based policy (bucket policy) to allow the Lambda function (identified by its ARN) to upload files to the bucket. This ensures the bucket accepts write actions from the Lambda function.

