# Tutorial Dojo - DVA-C02 - Summary

## Domain 1: Development with AWS Services

| No   |     | Q                                                                    | A                                                                                      | Ref                                                       |
| ---- | --- | -------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | --------------------------------------------------------- |
|      |     |                                                                      |                                                                                        |                                                           |
| I.4  | ❌  | AWS SAM: shift traffic to new version                                | SAM Deployment strategy                                                                | [SAM - Deploying gradually]                               |
| I.12 | ❌  | Lambda: Response to user after 5 min                                 | Lambda `Invoke` API `InvocationType`                                                   | [Invoke - InvocationType]                                 |
| I.14 | ❌  | S3: Remove PII before return to application                          | Use S3 Object Lambda to process object before return to application                    | [S3 Object Lambda] [S3 Object Lambda Use with CloudFront] |
| I.18 | ❌  | Only allow authorized clients to invalidate an API Gateway cache     | - API Gateway Additional settings / Per-key cache invalidation / Require authorization | [Invalidate an API Gateway cache entry]                   |
| I.21 | ❌  | Lambda: 50 requests/s; 100 s/request 👉️ 5.000 concurrency execution | Default quota of Lambda concurrency execution: 1.000 (can be increased to 10.000)      |                                                           |

## Domain 2: Security

| No  |     | Q                                                           | A                                                                                                                               | Ref |
| --- | --- | ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | --- |
|     |     |                                                             |                                                                                                                                 |     |
| I.1 | ❌  | Give a program to AWS services                              | - Best practice: EC2 instance profile (IAM Role)                                                                                |     |
| I.3 | ❌  | Database credential - How to encrypt & auto rotate?         | - AWS Secret Manager + Enable auto rotate                                                                                       |     |
| I.8 | ❌  | S3 - Ensure all objects are encryption at rest with SSE-KMS | Add a bucket policy which denies any s3:PutObject action unless the request includes the `x-amz-server-side-encryption` header. |     |

## Domain 3: Deployment

| No  |     | Q                                                                    | A                                                                                | Ref                                |
| --- | --- | -------------------------------------------------------------------- | -------------------------------------------------------------------------------- | ---------------------------------- |
|     |     |                                                                      |                                                                                  |                                    |
| I.1 | ❌  | Implement subscription with API Gateway                              | Use usage plan to distribute APIs & throttle usages based on defined limit/quota | [API Gateway - Usage plan]         |
| I.2 | ❌  | Lambda, pause task & wait for external process                       | Step Function - Callback pattern (SQS + SNS + Lambda)                            | [Step Function - Callback Pattern] |
| I.5 | ❌  | SAM template requires sections                                       | Transform & Resources                                                            |                                    |
| I.6 | ❌  | Create Lambda function with CLI error InvalidParameterValueException | Invalid parameter: maybe a role can't be assumed                                 |                                    |
| I.7 | ❌  | ECS schedule task based on CPU/memory                                | ECS - Task placement strategy: binpack, spread, random                           |                                    |

## Domain 4: Troubleshooting and Optimization

| No   |     | Q                                           | A                                                                                                   | Ref                                                        |
| ---- | --- | ------------------------------------------- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
|      |     |                                             |                                                                                                     |                                                            |
| I.6  | ❌  | Serve private content from CloudFront       | 1. Use signed-URL, sign-cookies                                                                     |                                                            |
| I.7  | ❌  | X-ray: How to debug?                        | `_X_AMZN_TRACE_ID` + `AWS_XRAY_CONTEXT_MISSING`                                                     |                                                            |
| I.12 | ❌  | CloudFront HTTPS                            | Viewer Protocol Policy: `Only HTTPS` or `Redirect HTTP to HTTPS`                                    |                                                            |
| I.14 | ❌  | DynamoDB Scan improve performance           | - Default page size: 1MB (Max) -> Reduce page size                                                  |                                                            |
| I.19 | ❌  | Use Lambda function inside a VPC            | - By default, Lambda is public (has internet access)                                                |                                                            |
| I.20 | ❌  | X-Ray filter trace                          | 1. Add `annotation` to record data used to group traces (indexed to used with `filter expression`)  |                                                            |
| I.22 | ❌  | API Gateway: Lambda Proxy - 502 Bad Gateway | In Lambda proxy integration, the backend Lambda function must return output according a JSON format | [Output format of a Lambda function for proxy integration] |
