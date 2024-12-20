# Tutorial Dojo - DVA-C02 - Timed Mode Set 5

Test time: Dec 9, 2023 (14:30)

Score: 47/65 (72%):

- CDA – Development with AWS Services 76.92% (20/26)
- CDA – Security 61.54% (8/13)
- CDA – Deployment 66.67% (6/9)
- CDA – Troubleshooting and Optimization 76.47% (13/17)

## Domain 1: Development with AWS Services

| No  |     | Q                                                                                                             | A                                                                                                                                         | Ref    |
| --- | --- | ------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ------ |
|     |     |                                                                                                               |                                                                                                                                           |        |
| 1   | ❌  | Lambda: Debug - Return log stream for the function instance                                                   | Use `context.logStreamName`                                                                                                               |        |
| 2   | ✅  | API Gateway & Lambda: New version. Smooth migration                                                           | Update Lambda function -> Deploy new version. Specify new ARN in API Gateway integration. Redeploy to new stage.                          |        |
| 3   | ✅  | Elastic Beanstalk: Path of config file                                                                        | /.ebextensions/xxx.config                                                                                                                 |        |
| 4   | ✅  | Lambda: Ephemeral storage                                                                                     | `/tmp`                                                                                                                                    |        |
| 5   | ✅  | Lambda: How to use Ruby?                                                                                      | Ruby's natively support                                                                                                                   |        |
| 6   | ✅  | CloudFront: Update image immediately                                                                          | Use file name versioning                                                                                                                  |        |
| 7   | ✅  | Cognito: Authentication with JWT                                                                              | 1. Create User Pools                                                                                                                      |        |
|     |     |                                                                                                               | 2. Create an authorizer with Cognito User Pool ID                                                                                         |        |
|     |     |                                                                                                               | 3. Set token source for authorization (to the name of header store JWT)                                                                   |        |
| 8   | ❌  | X-Ray: Group the trace                                                                                        | `Subsegment`: breakdown segment & provide granular timing detail about **downstream calls** (to AWS services, HTTP APIs, SQL queries)     |        |
|     |     |                                                                                                               | `Annotations`: key-pair values, indexed to used with `filter expression` 👉 _group traces_ (with console) or call `GetTraceSummaries` API |        |
|     |     |                                                                                                               | `Metadata`: key-pair values (not-indexed)                                                                                                 |        |
| 9   | ✅  | S3: Lowest cost                                                                                               | Glacier Deep Archive                                                                                                                      |        |
| 10  | ✅  | EC2: Run Apache web server                                                                                    | Use user-data to install and start Apache web server                                                                                      |        |
| 11  | ✅  | App host in 1 region. Re-create on other regions using AMI & CloudFormation. How?                             | Use Cfn Mapping & FindInMap                                                                                                               |        |
| 12  | ✅  | Serverless app. Application code & infrastructure code in Python. How?                                        | Use CDK and Python                                                                                                                        |        |
| 13  | ✅  | Step Functions: Handle error? Aggregate data in different states?                                             | Use Catch & ResultPath                                                                                                                    |        |
| 14  | ❌  | Step Functions: Break a task into multiple tasks (process synchronously)                                      | Step Functions **state** types:                                                                                                           | [1.14] |
|     |     |                                                                                                               | - Do some work: **Task** State & **Parallel** State                                                                                       |        |
|     |     |                                                                                                               | - Not do some work: **Wait** State, **Pass** State, **Choice** State, **Map** State, **Success/Fail** State.                              |        |
| 15  | ✅  | DynamoDB: Control access to individual items & attributes?                                                    | Fine-grain access control with                                                                                                            | [1.15] |
|     |     |                                                                                                               | 1. IAM policy                                                                                                                             |        |
|     |     |                                                                                                               | 2. Condition keys,                                                                                                                        |        |
|     |     |                                                                                                               | 2.1 `dynamodb:LeadingKeys`                                                                                                                |        |
|     |     |                                                                                                               | 2.2 `dynamodb:Attributes`                                                                                                                 |        |
|     |     |                                                                                                               | 3. IAM substitution variable e.g. `${www.amazon.com:user_id}`, `${graph.facebook.com:id}`, and `${accounts.google.com:sub}`               |        |
| 16  | ✅  | Cognito: UI for login page missing brand logo                                                                 | Cognito allows customization for: logo, CSS.                                                                                              |        |
| 17  | ✅  | SQS queue: messages larger than 256KB.                                                                        | Use Amazon S3, (for Java) Extended Client Library                                                                                         |        |
| 18  | ❌  | Lambda: Provide a public HTTPS endpoint & ensure it executes only if the request's from valid user            | 1. Use Lambda function URL                                                                                                                | [1.18] |
|     |     |                                                                                                               | 2. Auth type:                                                                                                                             |        |
|     |     |                                                                                                               | - ~~`AWS_IAM`~~                                                                                                                           |        |
|     |     |                                                                                                               | - `NONE`: The URL endpoint will be public                                                                                                 |        |
|     |     |                                                                                                               | 3. Implement your own authenticator logic in your function.                                                                               |        |
| 19  | ❌  | In-house authentication system, support sync user data between devices/platforms                              | Cognito Identity Pools - Developer-authenticated identities:                                                                              |        |
|     |     |                                                                                                               | - Use your own authenticated process                                                                                                      |        |
|     |     |                                                                                                               | - Use Cognito to sync user data between devices/platforms                                                                                 |        |
|     |     |                                                                                                               |                                                                                                                                           |        |
| 20  | ✅  | API Gateway: Integrate a XML-based SOAP API. How?                                                             | Use HTTP Integration:                                                                                                                     |        |
|     |     |                                                                                                               | - Integration Request: Map incoming request from JSON to XML (with `mapping template`)                                                    |        |
|     |     |                                                                                                               | - Integration Response: Map API response from XML back to JSON (with `mapping template`)                                                  |        |
| 21  | ✅  | Serverless: Send newsletter at 7-day interval. How?                                                           | Use `EventBridge` Schedule Rule to create events at 7-day interval, sends the events to `Lambda function` target                          |        |
| 22  | ❌  | DynamoDB: Python call `BatchGetItem` return partial data. Why? Fix?                                           | - `BatchGetItem` use more than the provisioned throughput limit                                                                           |        |
|     |     |                                                                                                               | - To fix this:                                                                                                                            |        |
|     |     |                                                                                                               | 1. Increase provisioned throughput                                                                                                        |        |
|     |     |                                                                                                               | 2. Wait for the load to DynamoDB reduces & try again:                                                                                     |        |
|     |     |                                                                                                               | - Implement your own retries with exponential backoff algorithm                                                                           |        |
|     |     |                                                                                                               | - Use AWS SDK to call `BatchGetItem` (comes with retries & exponential backoff)                                                           |        |
| 23  | ✅  | DynamoDB: Group multiple actions to multiple items to a one-or-nothing operation?                             | Use `TransactionWriteItems`                                                                                                               |        |
| 24  | ✅  | DynamoDB: When an item added to `Customer` table, dynamically update `Payment` table. How do it in real time? | Enable DynamoDB Streams for `Customer` table, trigger a Lambda function to update `Payment` table                                         |        |
| 25  | ✅  | ALB: Obtain all value of identical query parameter key.                                                       | Enable `multi-value headers`                                                                                                              |        |
| 26  | ✅  | ECS: 2 containers share logs. How?                                                                            | Define these 2 containers in 1 task definition, use EFS as a volume                                                                       |        |

[1.14]: https://docs.aws.amazon.com/step-functions/latest/dg/concepts-states.html
[1.15]: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/specifying-conditions.html
[1.18]: https://aws.amazon.com/blogs/aws/announcing-aws-lambda-function-urls-built-in-https-endpoints-for-single-function-microservices/

## Domain 2: Security

| No  |     | Q                                                                                        | A                                                                                                              | Ref                                             |
| --- | --- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
|     |     |                                                                                          |                                                                                                                |                                                 |
| 1   | ❌  | S3: Encryption each files with different keys. Cost-effective, low overhead              | - SSE-S3: use the same key for all files.                                                                      |                                                 |
|     |     |                                                                                          | - SSE-C & use KMS to create CMK for each files (`CreateKey`): not cost-effective (1CMK: 1$/month)              |                                                 |
|     |     |                                                                                          | - SSE-KMS & Use KMS to generate DEK for each files (`GenerateDataKey`): 👈 THIS                                |                                                 |
| 2   | ✅  | S3 bucket in production account. How to allow a user on dev account access?              | 1. In `prod` acc, create an IAM role                                                                           | [2.2]                                           |
|     |     |                                                                                          | 1.1 Give it just enough permission for its task)                                                               |                                                 |
|     |     |                                                                                          | 2.2 Specify the `dev` account as a `trusted entity`                                                            |                                                 |
|     |     |                                                                                          | 2. In `dev` acc, allow it to **assume role** of `prod` acc (created in step 1)                                 |                                                 |
|     |     |                                                                                          | 3. In `dev` acc, **switch role** to `prod` acc                                                                 |                                                 |
| 3   | ✅  | S3. Which service to allow user register/sign-in & upload/access images on S3.           | Cognito User Pools & Identity Pools                                                                            |                                                 |
| 4   | ✅  | Allow temporary access to EC2 & but still enforce MFA? Which STS API?                    | STS `GetSessionToken`                                                                                          |                                                 |
| 5   | ❌  | KMS features                                                                             |                                                                                                                |                                                 |
| 6   | ✅  | API Gateway: Regulate access to API & charge based on usage                              | Usage Plan                                                                                                     |                                                 |
| 7   | ✅  | Best practice to manage access key                                                       | Remote all access key of root account, use IAM role for applications                                           |                                                 |
| 8   | ✅  | Most secure way to send CW logs in EC2 instance of ASG launch configuration              | - Create a new IAM role for the new Launch Configuration                                                       |                                                 |
|     |     |                                                                                          | - Launch Configuration (deprecated), use Launch Template.                                                      |                                                 |
| 9   | ❌  | AWS CLI: `UnauthorizedOperation` error with encoded authorization message. What to do?   | Decode the message with `STS` `decode-authorization-message`                                                   | [2.9]                                           |
| 10  | ✅  | S3: Hundreds of thousands of objects. Turn on SSE-KMS. Performance degradation. Why?     | Requests to KMS are exceeded quota                                                                             |                                                 |
| 11  | ✅  | How to check permission of an IAM role?                                                  | 1. Use IAM Policy Simulator                                                                                    |                                                 |
|     |     |                                                                                          | 2. Run AWS CLI with `--dry-run`                                                                                |                                                 |
| 12  | ❌  | Serverless app defined with Cloud Development Kit (CDK). How to test local?              | 1. (From CDK template) "Synthesize" & output Cfn template with `cdk synth`                                     | [2.12 What is CDK?] [2.12 CDK toolkit commands] |
|     |     |                                                                                          | 2. Invoke the Lambda function locally with `sam invoke local` (by emulating the Lambda execution environment.) | [2.12 `sam local invoke`]                       |
| 13  | ❌  | Cognito Identity Pools: What does Cognito returns to authenticated/unauthenticated user? | - For authenticated users: Cognito returns the `token`                                                         |                                                 |
|     |     |                                                                                          | - For unauthenticated users: Cognito returns a `Cognito ID`                                                    |                                                 |

### 2.4 Requesting temporary security credentials with Security Token Service (STS)

| STS Token                 | What it does?                                                                   | Notes              |
| ------------------------- | ------------------------------------------------------------------------------- | ------------------ |
| AssumeRole                | cross-account **delegation** and federation through a custom identity broker    | Cross-account, MFA |
| AssumeRoleWithWebIdentity | federation through a **web-based** identity provider                            | SSO                |
| AssumeRoleWithSAML        | federation through an **enterprise** Identity Provider compatible with SAML 2.0 |                    |
| GetFederationToken        | federation through a custom identity broker                                     | Proxy app          |
| GetSessionToken           | temporary credentials for users in **untrusted environments**                   | MFA                |

Ref:

- <https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html>

### 2.5 KMS features

KMS features:

- Create symmetric/asymmetric keys
- Import symmetric keys
- Rotate symmetric keys
- Disable/Enable keys

Not a KMS features:

- Import asymmetric keys
- Rotate key in custom stores

[2.2]: https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html
[2.9]: https://docs.aws.amazon.com/STS/latest/APIReference/API_DecodeAuthorizationMessage.html
[2.12 What is CDK?]: https://docs.aws.amazon.com/cdk/v2/guide/home.html
[2.12 CDK toolkit commands]: https://docs.aws.amazon.com/cdk/v2/guide/cli.html#cli-commands
[2.12 `sam local invoke`]: https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/sam-cli-command-reference-sam-local-invoke.html

## Domain 3: Deployment

| No  |     | Q                                                                                         | A                                                                                                                                                      | Ref   |
| --- | --- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ----- |
|     |     |                                                                                           |                                                                                                                                                        |       |
| 1   | ✅  | CodeDeploy: S3 source. Deploy to EC2 fail during `DownloadBundle`                         | The EC2 instance profile don't have permission to access S3 bucket                                                                                     |       |
| 2   | ❌  | CodeDeploy: Rollback                                                                      | CodeDeploy rolls back deployments by **redeploying** a previously deployed revision of an application **as a new deployment** (with new deployment ID) | [3.2] |
| 3   | ✅  | Deploy to 3 environments: `test`, `staging`, `production`. How?                           | Use 3 `deployment group`s, each for 1 environment.                                                                                                     |       |
| 4   | ✅  | Elastic Beanstalk: Multi-container Docker. Which file to configure container definitions? | `Dockerrun.aws.json`                                                                                                                                   |       |
| 5   | ✅  | Elastic Beanstalk: Multi developers deploy without upload the whole project?              | Use `eb deploy` to deploy from local `CodeCommit` repo                                                                                                 |       |
| 6   | ✅  | Serverless app defined with CDK. Deploy to new account. `NoSuchBucket` error. Fix?        | Run `cdk bootstrap` to provision resources for CDK deployment, e.g. IAM role, S3 bucket.                                                               |       |
| 7   | ❌  | CodeCommit: How to setup for a new user?                                                  | Use AWS credential (with `credential-helper`)                                                                                                          | [3.7] |
| 8   | ✅  | CodeCommit: Forgot to pull master. Fix conflict?                                          | `git rebase` `feature` branch on `master` branch. Then manually fix conflict.                                                                          |       |
| 9   | ❌  | SAM: How to deploy (& test)?                                                              | 1. (Once time) `sam init`                                                                                                                              |       |
|     |     |                                                                                           | 2. `sam deploy`                                                                                                                                        |       |

[3.2]: https://docs.aws.amazon.com/codedeploy/latest/userguide/deployments-rollback-and-redeploy.html

### 3.7 CodeCommit: Setup for new user

- HTTPs Git credential (use username & password)

- SSH connections (use public-private key pair)

  - Create public & private key pair on your local machine
  - Associate the public key with IAM user

- Use AWS credential (profile)

  1. Use `git-remote-commit` (recommended)
  2. Use `aws codecommit` `credential-helper`

[3.7]: https://docs.aws.amazon.com/codecommit/latest/userguide/setting-up.html

## Domain 4: Troubleshooting and Optimization

| No  |     | Q                                                                                                                              | A                                                                                                                                                         | Ref    |
| --- | --- | ------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ |
|     |     |                                                                                                                                |                                                                                                                                                           |        |
| 1   | ❌  | Lambda: Function created with Cfn doesn't send logs to CW?                                                                     | Modify `ExecutionRole` & add `AWSLambdaBasicExecutionRole` managed policy                                                                                 |        |
|     |     |                                                                                                                                | - (Attach to Lambda's resourced-based policy won't works)                                                                                                 |        |
|     |     |                                                                                                                                | - When created with Web Console, the console automatically add these policy to execution role for us                                                      |        |
|     |     |                                                                                                                                | - With Cfn, we need to do it ourself.                                                                                                                     |        |
| 2   | ❌  | ECS: EC2 launch type. Terminate an instance (after it's stopped), but the container instance still appear in ECS cluster       | Terminate an instance:                                                                                                                                    |        |
|     |     |                                                                                                                                | - In `running` state, it will be automatically deregistered with ECS cluster                                                                              |        |
|     |     |                                                                                                                                | = In `stopped` state, it won't be                                                                                                                         |        |
|     |     |                                                                                                                                |                                                                                                                                                           |        |
|     |     |                                                                                                                                |                                                                                                                                                           |        |
| 3   | ✅  | CodeBuild: Run on a proxy server. `RequestError` when CodeBuild is accessed. Fix?                                              |                                                                                                                                                           |        |
| 4   | ❌  | API Gateway: Enable API caching. How to test the function without caching?                                                     | 0. Create a resource-based policy to allows the API Gateway execution service to invalidate the cache for requests on the specified resource              | [4.4]  |
|     |     |                                                                                                                                | 1. Make a request with `Cache-Control: max-age=0` header                                                                                                  |        |
| 5   | ✅  | S3 - Event Notifications: Compress the images, but it takes too much time. Improve?                                            | Increase memory ➡️ increase CPU                                                                                                                           |        |
| 6   | ✅  | Debug latency of your app (with recently added function)? How to do with X-Ray?                                                | Define sug-segments inside the function to "instrument" (measure) it                                                                                      |        |
| 7   | ✅  | AWS CLI: Create snapshot of EC2 instance. `InvalidInstanceID.NotFound`. Why?                                                   | Maybe the AWS CLI is using a profile for a different region                                                                                               |        |
| 8   | ✅  | Build a CI pipeline. Which AWS services?                                                                                       | CodeCommit, Lambda, CodeBuild                                                                                                                             |        |
| 9   | ✅  | Step Functions: Handle & recover from State's exception.                                                                       | Use `Catch` & `Retry` fields in state machine definition                                                                                                  |        |
| 10  | ✅  | Lambda - Cold start: Optimize?                                                                                                 | 1. Reduce pre-handler code                                                                                                                                |        |
|     |     |                                                                                                                                | 2. Increase CPU (by increasing memory)                                                                                                                    |        |
| 11  | ✅  | LAMP stack. Migrate to AWS?                                                                                                    | EC2 + Aurora/RDS                                                                                                                                          |        |
| 12  | ✅  | Lambda: process file (5min). So slow?                                                                                          | Change `InvokeType` to `Event` (asynchronous invocation)                                                                                                  |        |
| 13  | ❌  | DynamoDB: Optimize `Scan` in low-demand time?                                                                                  | **Parallel scan**: distribute workload across the partitions of the table (by passing `Segment` and `TotalSegments` parameters into the `Scan` operation) | [4.13] |
| 14  | ✅  | Website (hosted on S3) call API Gateway. `No "Access-Control-Allow-Origin"` error. Fix?                                        | Config CORS for API Gateway to allow the website (S3)                                                                                                     |        |
| 15  | ✅  | API Gateway + Lambda: Publish a new version of `AccService:Prod` with the alias `AccService:Beta`. How to test before promote? | Create a `BETA` stage. Use stage variable to reference the `beta` function alias                                                                          |        |
| 16  | ✅  | Lambda: `Unable to import module`. Fix?                                                                                        | 1. Install the missing module locally.                                                                                                                    |        |
|     |     |                                                                                                                                | 2. Package it with the handler or in a layer                                                                                                              |        |
|     |     |                                                                                                                                | 3. Re-upload to Lambda                                                                                                                                    |        |
| 17  | ✅  | Elastic Beanstalk: Keep the old code in S3 bucket. How?                                                                        | Change `Retention` to `Retain source bundle in S3`                                                                                                        |        |

[4.4]: https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-caching.html#invalidate-method-caching
[4.13]: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Scan.html#Scan.ParallelScan
