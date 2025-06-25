## Salesforce Connect Adapter for GraphQL on AWS—Partner Solution

For architectural details, step-by-step instructions, and customization options, see the [blog post](https://aws.amazon.com/blogs/apn/how-to-resolve-customer-issues-faster-with-salesforce-connect-and-amazon-rds-integration/).

For creating the S3 bucket, use Bucket policy:
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowPublicReadForAllObjects",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::<YOUR_BUCKET_NAME>/*"
    }
  ]
}
```
Replace <YOUR_BUCKET_NAME> with the actual bucket name.

This policy ensures all nested templates, schemas, and resolver artifacts are publicly readable during stack creation.
