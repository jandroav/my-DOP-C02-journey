# :dizzy: my-DOP-C02-journey (AWS Certified DevOps Engineer - Professional)

I would like to share my journey to get the AWS Certified DevOps Engineer - Professional certification. I hope this information can help you to prepare your exam.

## :muscle: Prepare your exam

I did the following courses to prepare my exam:

### :movie_camera: Courses and practice exams

* [AWS Certified DevOps Engineer Professional 2024 - DOP-C02](https://www.udemy.com/course/aws-certified-devops-engineer-professional-hands-on/?kw=AWS+Certified+DevOps+Engineer+-+Professional+2024&src=sac&couponCode=LETSLEARNNOWPP)
* [Practice Exams | AWS Certified DevOps Engineer Professional](https://www.udemy.com/course/aws-certified-devops-engineer-professional-practice-exam-dop/?couponCode=LETSLEARNNOWPP)
* [AWS Certified DevOps Engineer Professional Exam Guide Study Path DOP-C0](https://tutorialsdojo.com/aws-certified-devops-engineer-professional-exam-guide-study-path-dop-c01-dop-c02/)
* [AWS Certified DevOps Engineer Professional Practice Exams DOP-C02 2024](https://portal.tutorialsdojo.com/courses/aws-certified-devops-engineer-professional-practice-exams/) **(Very good practice exams, close to the real exam)**

### :closed_book: Books

* [AWS CERTIFIED DEVOPS ENGINEER PROFESSIONAL | MASTER THE EXAM (DOP-C02): 8 PRACTICE TESTS, 600 RIGOROUS QUESTIONS, GAIN WEALTH OF INSIGHTS, EXPERT EXPLANATIONS AND ONE ULTIMATE GOAL](https://www.amazon.es/gp/product/B0CP9YWL7P/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1)

## :heavy_check_mark: Exam tips

This is a list of tips that I found useful to prepare the exam:

### :green_book: Certification notes

* You don't usually set a Lambda function as the origin for your CloudFront distribution. You have to use Lambda@Edge instead
* Amazon GuardDuty is a threat detection service that continuously monitors for malicious activity and unauthorized behavior to protect your AWS accounts
* AWS Shield is a managed Distributed Denial of Service (DDoS) protection service and not an automated security assessment
* Amazon Inspector is an automated security assessment service that helps improve the security and compliance of applications deployed on AWS
* You cannot whitelist an IP address using a Security Group
* field-level encryption configuration is primarily used for safeguarding sensitive fields in your CloudFront
* AWS Config is a service that is primarily used to assess, audit, and evaluate the configurations of your AWS resources but not to diagnose and troubleshoot problems in your EC2 instance
* AWS Systems Manager State Manager is primarily used as a secure and scalable configuration management service that automates the process of keeping your Amazon EC2 and hybrid infrastructure in a state that you define but does not help you in troubleshooting your EC2 instances
* Sticky sessions just bind user sessions to a specific target group, thus, you're still persistently storing session data locally on the instance
* You have to integrate the S3 bucket with CloudFront and use Lambda@Edge to add the required headers
* You can't return an HTTP response with the required security headers by simply configuring the bucket policy of the S3 bucket
* Configuring a custom Request and Response Behavior in CloudFront is not enough to automatically add the required security headers to the HTTP response. You have to use Lambda@Edge to add the headers to satisfy the requirement of this scenario.
* You cannot add a local secondary index to an already existing table
* The custom remediation actions in AWS Config should be used in conjunction with AWS Systems Manager Automation documents
* You cannot use AWS Lambda as a notification target for the lifecycle hook of an Auto Scaling group. You can only configure Amazon CloudWatch Events, Amazon SNS, or Amazon SQS as notification targets.
* There is no Events tab on the CodeCommit repository settings
* For CodeCommit you have to use Amazon SNS instead of Amazon SES
* For CodeCommit you can't send notifications directly to CloudWatch Logs. You have to use Amazon SNS or a Lambda trigger first
* You cannot set an S3 bucket or object as a target for a CloudWatch Events rule
* You can’t directly send the S3 server access logs to CloudWatch logs
* You can’t use CloudWatch Events to filter your log groups directly
* There is no Canary deployment configuration in Elastic Beanstalk. This type of deployment strategy is usually used in Lambda
* Elastic Beanstalk cannot deploy Lambda functions and API Gateway
* You can't directly fetch the media files from your tape gateway in real-time since this is backed up using Glacier
* You won't be able to connect your tape gateway directly to your Kinesis Video Streams service. You need to use the AWS Storage Gateway first
* CodePipeline does not provide a feature for conditional actions
* Reverting to a previous version of an API/stage does not create a new deployment, so the CreateDeployment-related event will not be emitted, and the EventBridge rule will never be triggered
* AWS Lambda function to replicate all data across regions is not a scalable solution
* Global DynamoDB Tables, it will not automatically create new replica tables on all AWS regions. You have to manually specify and create the replica tables in the specific AWS regions where you want to replicate your data. Take note as well that the DynamoDB Stream option must be enabled in order for the Global DynamoDB Table to work
* Multi-Master Amazon Aurora database does not work across multiple regions by default
* X-Ray is primarily using the UDP port 2000 so this should also be added alongside the TCP port mapping
* It is better to configure your ECS task definitions instead of the Amazon ECS container agent to enable X-Ray
* Deletion policy is primarily used to preserve, and in some cases, backup a resource when the stack is deleted
* You can’t directly set CloudWatch Alarms to update the ECS task count. You have to use CloudWatch Events instead
* Global tables do not have read replicas
* The standby instance of an Amazon RDS Multi-AZ database can only be placed in the same AWS region where the primary instance is hosted
* You cannot create a snapshot using the Amazon RDS scheduled instance lifecycle events
* The AWS Trusted Advisor doesn’t provide any information regarding AWS-initiated RDS events. You should use the AWS Health API instead
* GSI does not support strong read consistency
* SCPs in AWS Organizations do not have the ability to enforce the encryption of EBS volumes using KMS when they are created in a CloudFormation stack. SCPs only provide central control over the maximum available permissions for all accounts in your organization, ensuring that your accounts stay within your organization’s access control guidelines
* CloudWatch Logs metric filters are primarily used to turn log data into numerical CloudWatch metrics that you can graph or set an alarm on. While you could create a metric filter for a specific error code, it wouldn’t directly give you the total count of that error code over a specific past time period. Metric filters are more about monitoring real-time data
* The xray-daemon.config configuration file is primarily used in Elastic Beanstalk
* CloudWatch Logs subscription cannot be directly integrated with an AWS Step Functions application
* RefreshCache API is exclusively accessible in file gateway mode and not supported in volume gateway mode
* You can directly call the EC2 CreateSnapshot API from CloudWatch Events
* The WaitOnResourceSignals property should be set to false instead of true, to determine what prevents the Auto Scaling group from being updated correctly during a stack update.
* Although ELB access logs contain latency information, you still need to parse the data using Lambda. The calculation process entails a significant amount of time. A faster solution would be to use Amazon CloudWatch metrics.
* SCPs are used in AWS Organizations to set fine-grained permissions for your accounts. An SCP that denies the iam:CreateUser action would effectively prevent the creation of new IAM users in the data analytics team’s AWS account, regardless of the permissions granted to the IAM entities in the account.
* By setting up an S3 event notification, any replication failures can automatically trigger a Lambda function without manual intervention. The Lambda function can then use S3 batch operations to efficiently retry replicating multiple failed objects in parallel.
* The aws:downloadContent plugin supports downloading SSM documents from GitHub
* The template constraint just limits the options that are available to end-users when they launch a product. It works by narrowing the allowable values for parameters that are defined in the product’s underlying AWS CloudFormation template.
* Amazon CloudWatch Logs Insights allows you to query and analyze CloudWatch logs, it does not have an integration with Amazon EventBridge (Amazon CloudWatch Events)
* You can’t directly use Step Functions in conjunction with AWS Config
* You can directly call the EC2 CreateSnapshot API from CloudWatch Events
