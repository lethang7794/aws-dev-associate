# Tutorial Dojo - DVA-C02 - Timed Mode Set 4

Test time: Dec 8 2023, 10h00 - 10h50 (00:50:00)

Score: 60/65 (92.3%):

- CDA – Development with AWS Services 91.67% (33/36)
- CDA – Security 90.91% (10/11)
- CDA – Deployment 80% (4/5)
- CDA – Troubleshooting and Optimization 100% (13/13)

## Domain 1: Development with AWS Services

| No  |     | Q                                                                                                                      | A                                                                                                                                                 | Ref                                     |
| --- | --- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
|     |     |                                                                                                                        |                                                                                                                                                   |                                         |
| 1   | ✅  | Automatically watermark images uploaded to S3                                                                          | Use S3 Event Notification `s3:ObjectCreate:Put`. Send the event to Lambda function (destination)                                                  |                                         |
| 2   | ✅  | Lambda function: access RDS in private subnet                                                                          | Connect to the VPC                                                                                                                                |                                         |
| 3   | ✅  | API Gateway + Lambda: Map incoming request to integration request & vice versa                                         | AWS custom (Lambda custom)                                                                                                                        |                                         |
| 4   | ✅  | Which cache strategy ensured cached data is always up-to-date & stale data are automatically deleted?                  | Write-through + With TTL                                                                                                                          | [1.4]                                   |
| 5   | ✅  | DynamoDD: How to prevent data overwritten?                                                                             | Optimistic locking + Conditional writes (check version number)                                                                                    |                                         |
| 6   | ✅  | Database credential: How to encrypted & auto-rotate?                                                                   | Use Secrets Manager + Enable Automatic Rotation                                                                                                   |                                         |
| 7   | ✅  | S3: Use SQL to filter & retrieve only a subset data of an object?                                                      | S3 Select (supports CSV, JSON, Apache Parquet & compressed CSV, JSON)                                                                             | [1.7]                                   |
| 8   | ❌  | DynamoDB - GSI: Consumed throughput; Consistency?                                                                      | GSI has its own consumed throughput. GSI only supports eventually consistent read                                                                 |                                         |
| 9   | ✅  | DynamoDB - GSI: How much throughput to provision?                                                                      | GSI WCU >= Base table WCU                                                                                                                         |                                         |
| 10  | ✅  | DynamoDB: 2KB items - 10 writes/s - 20 eventually consistent reads/s. How much RCU/WCU?                                | 2KB ➡️ 1 strongly consistent read = 1 RCU ➡️ 1 eventually = 0.5 RCU ➡️ 20 eventually = 10 RCU                                                     |                                         |
|     |     |                                                                                                                        | 2KB ➡️ 1 write = 2 WCU ➡️ 10 writes = 20 WCU                                                                                                      |                                         |
| 11  | ✅  | 1 item = 17KB. 320 strongly consistent read/s. How much RCU?                                                           | 17KB/item ➡️ 5RCU/strongly consistent read ➡️ 320 strongly read = 320 x 5 = 1600 RCU                                                              |                                         |
| 12  | ✅  | HTML, JS, image, video. How to server with lowest latency around the world?                                            | S3 + CloudFront                                                                                                                                   |                                         |
| 13  | ✅  | AI-based app built with Lambda. How to modify the way invocation event are read form Lambda runtime API?               | Use Lambda custom runtime                                                                                                                         |                                         |
| 14  | ✅  | Migrate monolith on-premise app to Lambda. Best practice?                                                              | 1. Take advantage of `execution runtime`; 2. Use environment variable...                                                                          | [1.14 Lambda Best Practice]             |
| 15  | ❌  | ECS: Tasks are scheduled on instances with enough resources. Which task placement strategy?                            | Random                                                                                                                                            |                                         |
| 16  | ✅  | Online game - Sync app pref + state of player + Allow multiple player to share state                                   | App Sync (Cognito Sync not support shared data)                                                                                                   |                                         |
| 17  | ✅  | AWS CLI in EC2 instance. How to easily switch role?                                                                    | 1. Create a new CLI profile with credential; 2. Run `aws` CLI with `--profile`                                                                    |                                         |
| 18  | ✅  | DynamoDB: Ensure item is updated only some attribute meets some condition                                              | Conditional writes                                                                                                                                |                                         |
| 19  | ✅  | DynamoDB: Debug throughput of both base table & GSI when update item?                                                  | Call `UpdateItem` with `ReturnConsumedCapacity` set to ~~`None`~~ / ~~`Total`~~ / `Indexes`                                                       | [1.19 PutItem - ReturnConsumedCapacity] |
| 20  | ✅  | DynamoDB Streams: How to integrate with Lambda?                                                                        | 1. Create an `EventSourceMapping` to poll the DynamoDB stream, read & process records                                                             |                                         |
|     |     |                                                                                                                        | 2. Give Lambda function enough permission to interact with DynamoDB via `ExecutionRole` (`AWSLambdaDynamoDBExecutionRole` managed policy)         |                                         |
| 21  | ✅  | Serverless app: Which service can manage configuration & deploy the whole stack + simple?                              | AWS SAM (Serverless Application Model)                                                                                                            |                                         |
| 22  | ✅  | DynamoDB: Table: ArticleName (PK) - Category (SK). Query ArticleName using another Sort Key + Strongly consistent read | Create a new table with Local Secondary Index (LSI). Migrate the existing data to new table (LSI cannot be created after the DynamoTB is created) |                                         |
| 23  | ✅  | S3: Ensure all objects are encrypted with AE256                                                                        | Use **bucket policy** to deny any Create request doesn't have `x-amz-server-side-encryption: AE256` header                                        |                                         |
| 24  | ✅  | EC2: Shell script to get instance public/private IP                                                                    | Use Instance Metadata Service endpoint 169.254.169.254/latest/meta-data                                                                           |                                         |
| 25  | ✅  | Lambda: Account concurrency limit 2000; 10 functions: 1 function 400, 1 function 200. The rest, the third?             | The rest: 1400; the third: 1300.                                                                                                                  |                                         |
| 26  | ✅  | Coordinate multiple services into serverless workflow. Which service?                                                  | AWS Step Functions                                                                                                                                |                                         |
| 27  | ✅  | API Gateway: Enable caching. How to invalidate 1 key?                                                                  | Send the request with `Cache-Control: max-age=0`                                                                                                  |                                         |
| 28  | ✅  | Lambda: Connection refused. Why?                                                                                       | Maybe the invoke URL is wrong (`http` without `s`)                                                                                                |                                         |
| 29  | ✅  | Lambda: Improve performance?                                                                                           | Increase memory will increase CPU too.                                                                                                            |                                         |
| 30  | ✅  | Lambda: A function initialize DB connection every time it executes. How to optimize?                                   | Move the DB connection to shared `execution context` (outside handler)                                                                            |                                         |
| 31  | ✅  | Lambda: Can the function built with Rust?                                                                              | Yes. Use custom runtime                                                                                                                           |                                         |
| 32  | ✅  | Lambda: A function fetch 20MB static data every time it executes. How to optimize?                                     | Place the initialize outside Lambda handler; saved external file to `/tmp`                                                                        |                                         |
| 33  | ❌  | Deploy containerized apps? ECS, EKS or Elastic Beanstalk?                                                              | Under the hood, Elastic Beanstalk uses ECS (& ELB, ASG)                                                                                           |                                         |
| 34  | ✅  | Online game. How to add feature to cross-sync profile data between device?                                             | Use Cognito Sync (or App Sync)                                                                                                                    |                                         |
| 35  | ✅  | DynamoDB: Which attribute to use as partition key?                                                                     | The partition should uniquely identify each item                                                                                                  |                                         |
| 36  | ✅  | CodePipeline: Push build details into a DynamoDB?                                                                      | Use EventBridge & Lambda                                                                                                                          |                                         |

[1.7]: https://docs.aws.amazon.com/AmazonS3/latest/userguide/selecting-content-from-objects.html
[1.14 Lambda Best Practice]: https://docs.aws.amazon.com/lambda/latest/dg/best-practices.html
[1.19 PutItem - ReturnConsumedCapacity]: https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_PutItem.html#DDB-PutItem-request-ReturnConsumedCapacity

### 1.4 Caching Strategies

|                          | What is it?                                                                                   | Pros                          | Cons                              |     |
| ------------------------ | --------------------------------------------------------------------------------------------- | ----------------------------- | --------------------------------- | --- |
|                          |                                                                                               |                               |                                   |     |
| Lazy-loading             | Loads data into the cache only when necessary (catches cache misses on reads)                 | Only requested data is cached | Cache miss read penalty (3 trips) |     |
|                          |                                                                                               |                               | Stale data                        |     |
| Write-through            | Loads data into the cache whenever data is written to the database (populates data on writes) | No stale data                 | Missing data (empty nodes)        |     |
|                          |                                                                                               | No read penalty               | Cache churn (not re-used cache)   |     |
| Lazy-loading (with TTL)  | An expired key is treated as not found                                                        |                               |                                   |     |
| Write-through (with TTL) |                                                                                               |                               |                                   |     |

[1.4]: https://docs.aws.amazon.com/AmazonElastiCache/latest/mem-ug/Strategies.html

## Domain 2: Security

| No  |     | Q                                                                                      | A                                                                                                                                                          | Ref   |
| --- | --- | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ----- |
|     |     |                                                                                        |                                                                                                                                                            |       |
| 1   | ❌  | 1 bucket - many users. How to redact PII & manage access permission?                   | Use S3 Object Lambda (+) Access Point                                                                                                                      |       |
| 2   | ✅  | SSM Parameter Store: Notify if param haven't been rotated for 90 days                  | 1. Use Advanced tier / Parameter polices / Notification policies                                                                                           |       |
|     |     |                                                                                        | - `NoChangeNotification` After `xxx`                                                                                                                       |       |
|     |     |                                                                                        | - ~~`ExpirationNotification`~~ Before `xxx`                                                                                                                |       |
|     |     |                                                                                        | - ~~`Expiration`~~                                                                                                                                         |       |
|     |     |                                                                                        | 2. Use EventBridge **rule** to filter & send `NoChangeNotification` event to a SNS topic (target)                                                          |       |
| 3   | ✅  | S3: Ensure data is encrypted at rest using the company key                             | 1. Client-Side Encryption (CSE) - Encrypt the data before send to S3                                                                                       |       |
|     |     |                                                                                        | 2. Server-Side Encryption (SSE) - Send the data with the encryption key                                                                                    |       |
|     |     |                                                                                        | 2.1 For CLI, Use the request headers: `x-amz-server-side​-encryption-customer` + `algorithm`/`key`/`key-MD5`                                               |       |
|     |     |                                                                                        | 2.2 Or use the SDK                                                                                                                                         |       |
| 4   | ✅  | KMS: Locally encrypt data (Envelope encryption)                                        | 1. Use the `GenerateDataKey` API to get a `data key`.                                                                                                      |       |
|     |     |                                                                                        | 2. Use the **plaintext** `data key` (`GenerateDataKey` response `Plaintext`) to encrypt data locally, then erase the **plaintext** `data key` from memory. |       |
|     |     |                                                                                        | 3. Store the **encrypted** `data key` (`GenerateDataKey` response `CiphertextBlob`) alongside the locally encrypted data.                                  |       |
|     |     |                                                                                        |                                                                                                                                                            |       |
| 5   | ✅  | API Gateway: Custom authorizer using bearer token (same as SAML, OAuth). How?          | Use API Gateway **Lambda authorizer** (aka custom authorizer)                                                                                              | [2.5] |
|     |     |                                                                                        | - Token-based Lambda authorizer (aka TOKEN authorizer) 👈 THIS ONE                                                                                         |       |
|     |     |                                                                                        | - Request parameter-based Lambda authorizer (aka REQUEST authorizer)                                                                                       |       |
| 6   | ✅  | Database credential + Rotate                                                           | Secrets Manager + Auto Rotation (How? Secrets Manager run a Lambda function )                                                                              | [2.6] |
| 7   | ✅  | CloudFormation: Retrieve license key + cost-effective                                  | Systems Manager Parameter Store + Secure String                                                                                                            |       |
| 8   | ✅  | Migrate on-premise to AWS. Integrate LDAP directory service (not compatible with SAML) | Implement a _custom_ **identity broker**, which use `STS` to issue short-live AWS credentials                                                              | [2.8] |
| 9   | ✅  | Cognito: Additional authentication method                                              | Integrate Multi-Factor Authentication (MFA) to Cognito User Pool                                                                                           |       |
| 10  | ✅  | SQL Server. Migrate to RDS. Encrypt data before write to disk & vice versa.            | Enable SQL Server Transparent Data Encryption                                                                                                              |       |
| 11  | ✅  | S3. Someone use your image without permission.                                         | (Block public access) Use pre-signed URL / pre-signed cookies                                                                                              |       |

[2.5]: https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-use-lambda-authorizer.html
[2.6]: https://aws.amazon.com/blogs/security/how-to-configure-rotation-windows-for-secrets-stored-in-aws-secrets-manager/
[2.8]: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_federated-users.html#id_roles_common-scenarios_federated-users-idbroker

## Domain 3: Deployment

| No  |     | Q                                                                                          | A                                                                              | Ref   |
| --- | --- | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ----- |
|     |     |                                                                                            |                                                                                |       |
| 1   | ❌  | SAM deploy process (From local machine)                                                    | 1. Build (local); ~~2. Package ("Publish" to S3)~~; 3. Deploy (Use artifact on S3) |       |
| 2   | ✅  | Elastic Beanstalk: HA, revert quickly?                                                     | 1. Use any EB deployment strategy, e.g. All-at-once (fastest)                  |       |
|     |     |                                                                                            | 2. Blue-Green deployment (EB calls it swap environment URLs)                   | [3.2] |
| 3   | ✅  | CloudFormation: Inline code in template                                                    | `AWS::Lambda::Function` / `Code` / `ZipFile`                                   |       |
| 4   | ✅  | Serverless app: Zip code, upload to S3, produce package deployment-ready template & deploy | `sam deploy` (which includes `sam package`)                                    |       |
| 5   | ✅  | CloudFormation: Install packages, start services on EC2 after provisioned                  | `cfn-init`                                                                     |       |

### 3.1 SAM deploy process

|     | npm                          | sam                                           |
| --- | ---------------------------- | --------------------------------------------- |
|     | npm init                     | sam init                                      |
|     | npm install                  |                                               |
|     |                              |                                               |
|     | npm build                    | **sam build**                                 |
|     | npm publish                  | ~~sam package~~ (deprecated, use sam deploy)  |
|     | npm start                    | **sam deploy**                                |
|     |                              | - sam list endpoints                          |
|     | - curl http//:localhost:3000 | - curl https//<>.execute-api.<>.amazonaws.com |
|     |                              |                                               |
|     | nodemon index.js             | sam sync --watch                              |

`sam deploy` now implicitly performs the functionality of `sam package`

Ref:

- <https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-deploying.html>

[3.2]: https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.CNAMESwap.html

## Domain 4: Troubleshooting and Optimization

| No  |     | Q                                                                                | A                                                                                          | Ref |
| --- | --- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | --- |
|     |     |                                                                                  |                                                                                            |     |
| 1   | ✅  | Send traces to X-ray?                                                            | Use X-Ray daemon (CloudWatch Agent can do this on EC2/On-Premise)                          |     |
| 2   | ✅  | SQS: Duplicate message. Fix?                                                     | Use FIFO queue + provide deduplicationID                                                   |     |
| 3   | ✅  | X-Ray: Filter trace?                                                             | 1. Use web console; 2. Use `GetTraceSummaries` (support search)                            |     |
| 4   | ✅  | X-Ray: Send trace to X-Ray?                                                      | - 1. Use X-Ray SDK (through X-Ray daemon); 2. Use X-Ray/CLI (directly)                     |     |
|     |     |                                                                                  | - `PutTraceSegments` API accepts a single segment document with many segments              |     |
| 5   | ✅  | Kinesis: Over-provision. Scale in?                                               | Merge **cold** shards                                                                      |     |
| 6   | ✅  | API Gateway: Terminated Lambda. Why?                                             | - Lambda timeout: max `15min` ➡️ `terminated`                                              |     |
|     |     |                                                                                  | - API Gateway timeout: `30s` for an integration ➡️ `504 Timeout`                           |     |
| 7   | ✅  | API Gateway: No metrics for CacheHitCount/CacheMissCount                         | API Gateway caching is not enabled                                                         |     |
| 8   | ✅  | SQS injections, XSS attack. How to deal?                                         | Use Web Application Firewall (WAF). It works with: CloudFront, ALB, API Gateway (REST API) |     |
| 9   | ✅  | Kinesis: 10 shards - 10 EC2 instance. Increase to 20 shards, how many instances? | 20 instances, the number of instances match the number of shards by `1:1` ratio            |     |
| 10  | ✅  | RDS: Monitor memory, CPU usages of processes?                                    | Use RDS enhanced monitoring                                                                |     |
| 11  | ✅  | CodePipeline: Code review in each stage before move to next stage                | Use a "manually approval" action, and send the approval request to a SNS topic             |     |
| 12  | ✅  | X-Ray: Record call to DB, other services, SQL queries & filter                   | Add **annotations** in the **subsegment** section of the **segment document**.             |     |
| 13  | ✅  | X-Ray: Permission to send trace to X-Ray?                                        | `AWSXRayDaemonWriteAccess`                                                                 |     |

### 4.1 How to send traces to X-ray?

1. X-Ray daemon

   The AWS X-Ray daemon is a software application that listens for traffic on **UDP** port **2000**, gathers raw segment data, and relays it to the AWS X-Ray API.

   The daemon works in conjunction with the AWS X-Ray SDKs and must be running so that data sent by the SDKs can reach the X-Ray service.

2. AWS Distro for OpenTelemetry (ADOT) Collector

3. (For EC2, On-premises) CloudWatch Agent can do this from `1.300025.0`

### 4.1 Setup X-Ray daemon

- Lambda: the deamon run automatically
- EC2:
  - Elastic Beanstalk: Enable with `XRayEnabled` configuration option
  - EC2: Install/Run manually (May use user data)
  - ECS:
    - Use official Docker image
    - Build custom Docker image
- On-premise: Install/Run manually

### 4.2 SQS: Duplicate messages

<https://aws.amazon.com/about-aws/whats-new/2016/11/amazon-sqs-introduces-fifo-queues-with-exactly-once-processing-and-lower-prices-for-standard-queues/>
<https://docs.aws.amazon.com/AWSSimpleQueueService/latest/APIReference/API_SendMessage.html#SQS-SendMessage-request-MessageDeduplicationId>

### 4.8 AWS WAF, AWS Firewall Manager, and AWS Shield Advanced

<https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html>

### 4.9 Scale Kinesis Data Streams

To scale up processing in your application, you should test a combination of these approaches:

- Increasing the instance size (because all record processors run in parallel within a process)
- Increasing the number of instances up to the maximum number of open shards (because shards can be processed independently)
- Increasing the number of shards (which increases the level of parallelism)

<https://docs.aws.amazon.com/streams/latest/dev/kinesis-record-processor-scaling.html>

### 4.10 Monitor RDS

- CloudWatch (default): RDS automatically sends metrics to CloudWatch every minute (from hypervisor for the DB instance - "outside")
- RDS Enhanced Monitoring:
  - Gather metrics about the OS: processes, memory... (from an agent on the DB instance - "inside")
  - Logs are sent to CloudWatch Logs

[Differences between CloudWatch and Enhanced Monitoring metrics](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Monitoring.OS.overview.html#USER_Monitoring.OS.CloudWatchComparison)

### 4.11 Manage approval actions in CodePipeline

<https://docs.aws.amazon.com/codepipeline/latest/userguide/approvals.html>
