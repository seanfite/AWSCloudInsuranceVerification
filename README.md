# CloudInsuranceVerification

This project creates an executable that accepts a command line call to upload a file to an S3 bucket. A Lambda function 
has a PUT trigger on this S3 bucket and processes the file to parse out patient data. A JSON file is created with the 
results and sent to an SQS queue. A worker service is waiting for queue messages and compares the JSON file with a local 
database to confirm validity. The results are sent back into a SQS queue to print the results to user that uploaded the S3 
bucket file.
