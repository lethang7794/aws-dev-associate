# Tutorial Dojo - DVA-C02 - Timed Mode Set 5

Test time: Dec 9, 2023 (14:30)

Score: 47/65 (72%):

- CDA – Development with AWS Services 76.92% (20/26)
- CDA – Security 61.54% (8/13)
- CDA – Deployment 66.67% (6/9)
- CDA – Troubleshooting and Optimization 76.47% (13/17)

## Domain 1: Development with AWS Services

| No  |     | Q                                                                                                  | A                                                                                                                                         | Ref    |
| --- | --- | -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ------ |
|     |     |                                                                                                    |                                                                                                                                           |        |
| 1   | ❌  | Lambda: Debug - Return log stream for the function instance                                        | Use `context.logStreamName`                                                                                                               |        |
| 2   | ✅  |                                                                                                    |                                                                                                                                           |        |
| 3   | ✅  |                                                                                                    |                                                                                                                                           |        |
| 4   | ✅  |                                                                                                    |                                                                                                                                           |        |
| 5   | ✅  |                                                                                                    |                                                                                                                                           |        |
| 6   | ✅  |                                                                                                    |                                                                                                                                           |        |
| 7   | ✅  |                                                                                                    |                                                                                                                                           |        |
| 8   | ❌  | X-Ray: Group the trace                                                                             | `Subsegment`: breakdown segment & provide granular timing detail about **downstream calls** (to AWS services, HTTP APIs, SQL queries)     |        |
|     |     |                                                                                                    | `Annotations`: key-pair values, indexed to used with `filter expression` 👉 _group traces_ (with console) or call `GetTraceSummaries` API |        |
|     |     |                                                                                                    | `Metadata`: key-pair values (not-indexed)                                                                                                 |        |
| 9   | ✅  |                                                                                                    |                                                                                                                                           |        |
| 10  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 11  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 12  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 13  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 14  | ❌  | Step Functions: Break a task into multiple tasks (process synchronously)                           | Step Functions **state** types:                                                                                                           | [1.14] |
| 15  | ✅  |                                                                                                    | - Do some work: **Task** State & **Parallel** State                                                                                       |        |
| 16  | ✅  |                                                                                                    | - Not do some work: **Wait** State, **Pass** State, **Choice** State, **Map** State, **Success/Fail** State.                              |        |
| 17  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 18  | ❌  | Lambda: Provide a public HTTPS endpoint & ensure it executes only if the request's from valid user | 1. Use Lambda function URL                                                                                                                | [1.18] |
|     |     |                                                                                                    | 2. Auth type:                                                                                                                             |        |
|     |     |                                                                                                    | - ~~`AWS_IAM`~~                                                                                                                           |        |
|     |     |                                                                                                    | - `NONE`: The URL endpoint will be public                                                                                                 |        |
|     |     |                                                                                                    | 3. Implement your own authenticator logic in your function.                                                                               |        |
| 19  | ❌  | In-house authentication system, support sync user data between devices/platforms                   | Cognito Identity Pools - Developer-authenticated identities:                                                                              |        |
|     |     |                                                                                                    | - Use your own authenticated process                                                                                                      |        |
|     |     |                                                                                                    | - Use Cognito to sync user data between devices/platforms                                                                                 |        |
|     |     |                                                                                                    |                                                                                                                                           |        |
| 20  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 21  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 22  | ❌  | DynamoDB: Python call `BatchGetItem` return partial data. Why? Fix?                                | - `BatchGetItem` use more than the provisioned throughput limit                                                                           |        |
|     |     |                                                                                                    | - To fix this:                                                                                                                            |        |
|     |     |                                                                                                    | 1. Increase provisioned throughput                                                                                                        |        |
|     |     |                                                                                                    | 2. Wait for the load to DynamoDB reduces & try again:                                                                                     |        |
|     |     |                                                                                                    | - Implement your own retries with exponential backoff algorithm                                                                           |        |
|     |     |                                                                                                    | - Use AWS SDK to call `BatchGetItem` (comes with retries & exponential backoff)                                                           |        |
| 24  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 25  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 26  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 27  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 28  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 29  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 30  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 30  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 31  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 32  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 33  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 34  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 35  | ✅  |                                                                                                    |                                                                                                                                           |        |
| 36  | ✅  |                                                                                                    |                                                                                                                                           |        |

[1.14]: https://docs.aws.amazon.com/step-functions/latest/dg/concepts-states.html
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

| No  |     | Q                                                                                                                        | A                                                                                                                                                         | Ref    |
| --- | --- | ------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ |
|     |     |                                                                                                                          |                                                                                                                                                           |        |
| 1   | ❌  | Lambda: Function created with Cfn doesn't send logs to CW?                                                               | Modify `ExecutionRole` & add `AWSLambdaBasicExecutionRole` managed policy                                                                                 |        |
|     |     |                                                                                                                          | - (Attach to Lambda's resourced-based policy won't works)                                                                                                 |        |
|     |     |                                                                                                                          | - When created with Web Console, the console automatically add these policy to execution role for us                                                      |        |
|     |     |                                                                                                                          | - With Cfn, we need to do it ourself.                                                                                                                     |        |
| 2   | ❌  | ECS: EC2 launch type. Terminate an instance (after it's stopped), but the container instance still appear in ECS cluster | Terminate an instance:                                                                                                                                    |        |
|     |     |                                                                                                                          | - In `running` state, it will be automatically deregistered with ECS cluster                                                                              |        |
|     |     |                                                                                                                          | = In `stopped` state, it won't be                                                                                                                         |        |
|     |     |                                                                                                                          |                                                                                                                                                           |        |
|     |     |                                                                                                                          |                                                                                                                                                           |        |
| 3   | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 4   | ❌  | API Gateway: Enable API caching. How to test the function without caching?                                               | 0. Create a resource-based policy to allows the API Gateway execution service to invalidate the cache for requests on the specified resource              | [4.4]  |
|     |     |                                                                                                                          | 1. Make a request with `Cache-Control: max-age=0` header                                                                                                  |        |
| 5   | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 6   | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 7   | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 8   | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 9   | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 10  | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 11  | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 12  | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 13  | ❌  | DynamoDB: Optimize `Scan` in low-demand time?                                                                            | **Parallel scan**: distribute workload across the partitions of the table (by passing `Segment` and `TotalSegments` parameters into the `Scan` operation) | [4.13] |
| 14  | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 15  | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 16  | ✅  |                                                                                                                          |                                                                                                                                                           |        |
| 17  | ✅  |                                                                                                                          |                                                                                                                                                           |        |

[4.4]: https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-caching.html#invalidate-method-caching
[4.13]: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Scan.html#Scan.ParallelScan
