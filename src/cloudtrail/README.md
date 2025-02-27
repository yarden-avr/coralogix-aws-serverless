# AWS cloud trail integarion for Coralogix

Coralogix provides a predefined Lambda function to easily forward your CloudTrail logs straight to the Coralogix platform.

## Prerequisites
* Active CloudTrail 
* Permissions to create lambda functions
* An AWS account.
* A coralogix account.

## AWS Resource Manager Template Deployment

The Cloud trail integration can be deployed by clicking the link below and signing into your AWS account:

[deployment link](https://serverlessrepo.aws.amazon.com/applications/eu-central-1/597078901540/Coralogix-CloudTrail)

The application should be installed in the same AWS region as the CloudWatch log group. Make sure that after you click on deploy for the application, that you are in right region.

## Fields

**Application name** - The stack name of this application created via AWS CloudFormation.

**NotificationEmail** (optinal) - If the lambda fails a notification email will be sent to this address via SNS (requires you have a working SNS, with a validated domain).

**S3BucketName** - The name of the S3 bucket with CloudTrail logs to watch (must be in the same region as stack that you will create).

**ApplicationName** - Application Name as it will be seen in Coralogix UI.

**CoralogixRegion** - The Coralogix location region, possible options are [Europe, Europe2, India, Singapore, US].In case that you want to use Custom domain, leave this as default and write the Custom doamin in the ``CustomDomain`` filed.

**CustomDomain** - The Coralogix custom domain,leave empty if you don't use Custom domain.

**FunctionArchitecture** - Lambda function architecture, possible options are [x86_64, arm64]. 

**FunctionMemorySize** - The maximum allocated memory this lambda may consume, the default is 1024. Don't change

**FunctionTimeout** - The maximum time in seconds the function may be allowed to run, the default is 300. Don't change

**PrivateKey** - Your Coralogix secret key.

**SubsystemName** - Sybsystem Name as it will be seen in Coralogix UI.

**S3KeyPrefix** - The prefix of the path within the log, this way you can choose if only part of your bucket is shipped.

**S3KeySuffix** - A filter for the suffix of the file path in your bucket, the default is .json.gz.

Do not change the `FunctionMemorySize`, `FunctionTimeout` parameters.

## License

This project is licensed under the Apache-2.0 License.
