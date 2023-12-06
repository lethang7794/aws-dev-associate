# Tutorial Dojo - DVA-C02 - Timed Mode Set 2

Test time: 9h45 - 10h28 (00:47:24)

Score: 50/65 (76.92%):

- CDA – Development with AWS Services 79.49%
- CDA – Security 77.78%
- CDA – Deployment 87.5%
- CDA – Troubleshooting and Optimization 55.56%

## Domain 1: Development with AWS Services

| No    | Q                                                                                                    | A                                                                                                             | Ref                                                                           |
| ----- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| 1     |                                                                                                      |                                                                                                               |                                                                               |
| 2     |                                                                                                      |                                                                                                               |                                                                               |
| 3     |                                                                                                      |                                                                                                               |                                                                               |
| 4     |                                                                                                      |                                                                                                               |                                                                               |
| 5     |                                                                                                      |                                                                                                               |                                                                               |
| 6     |                                                                                                      |                                                                                                               |                                                                               |
| 7 ❌  | Tracking number of visitors on website (use DynamoDB)                                                | 1. (May over/under count) "Atomic counter" - just increase the counter without checking current value         |                                                                               |
|       |                                                                                                      | 2. Use `condition write` to only update the counter item if (...) - too complicated to know                   | [Conditional Writes - DynamoDB] [Conditional Updates - DynamoDB]              |
| 8 ❌  | Kinesis Data Streams: Duplicate Records                                                              | - Two primary reasons: 1. Producer retries; 2. Consumer retries.                                              | [Handling Duplicate Records - Kenesis]                                        |
|       |                                                                                                      | - Manually assign sequence number to record with `Kinesis` `PutRecord` `SequenceNumberForOrdering`.           | [Adding a Single Record - Kenesis]                                            |
|       |                                                                                                      | (Same idea as assign an ID to message `SQS` `SendMessage` `MessageDeduplicationId` )                          |                                                                               |
| 9 ❌  | X-Ray: Include info about calls to AWS services                                                      | Include `sub-segment` in the `segment document`                                                               |                                                                               |
| 10 ❌ | DynamoDB: Forum (PK) - Subject (SK) - LastPostUpdateTime. Finds on posts of a forum in last 3 months | Add LSI: Forum (PK) - LastPostUpdatTime (SK). Use `Query` opeartion.                                          |                                                                               |
| 11    |                                                                                                      |                                                                                                               |                                                                               |
| 12    |                                                                                                      |                                                                                                               |                                                                               |
| 13    |                                                                                                      |                                                                                                               |                                                                               |
| 14    |                                                                                                      |                                                                                                               |                                                                               |
| 15    |                                                                                                      |                                                                                                               |                                                                               |
| 16    |                                                                                                      |                                                                                                               |                                                                               |
| 17    |                                                                                                      |                                                                                                               |                                                                               |
| 18    |                                                                                                      |                                                                                                               |                                                                               |
| 19 ❌ | Elastic Beanstalk: Deploy infrastructure has an RDS instance coupling with EB. How to migrate RDS?   | 1. Create RDS snapshot; enable RDS deletion protection                                                        |                                                                               |
|       |                                                                                                      | 2. Remove SG attached to RDS (before delete EB app's environment)                                             |                                                                               |
|       |                                                                                                      | 3. Terminate the EB app's environment                                                                         |                                                                               |
| 20    |                                                                                                      |                                                                                                               |                                                                               |
| 21    |                                                                                                      |                                                                                                               |                                                                               |
| 22    |                                                                                                      |                                                                                                               |                                                                               |
| 23    |                                                                                                      |                                                                                                               |                                                                               |
| 24    |                                                                                                      |                                                                                                               |                                                                               |
| 25    | DynamoDB: Store recent updated item automatically                                                    | 1. DynamoDB Streams + Lambda (not recommnend)                                                                 |                                                                               |
|       |                                                                                                      | 2. DynamoDB Streams + DynamoDB Streams Kinesis Adapter (recommend)                                            |                                                                               |
| 26    |                                                                                                      |                                                                                                               |                                                                               |
| 27    |                                                                                                      |                                                                                                               |                                                                               |
| 28    |                                                                                                      |                                                                                                               |                                                                               |
| 29    |                                                                                                      |                                                                                                               |                                                                               |
| 30    |                                                                                                      |                                                                                                               |                                                                               |
| 31 ❌ | Lambda: Concurrency quotas                                                                           | - Account-level: 1.000 unit of concurrency                                                                    | [Lambda Concurrency Quotas]                                                   |
|       |                                                                                                      | - Function-level: Up-to 900 unit of concurrency. AWS reservers 100 for functions without reserved concurrency |                                                                               |
| 32    |                                                                                                      |                                                                                                               |                                                                               |
| 33 ❌ | Elastic Beanstalk: Environment manifest (environment name, solution stack...)                        | - Environment manifest: `/env.yaml`                                                                           | [Environment manifest (env.yaml) - Elastic Beanstalk]                         |
|       |                                                                                                      | - Advance config: `/.ebextensions/***.config` (YAML or JSON)                                                  | [Advanced environment customization with configuration files (.ebextensions)] |
| 34    |                                                                                                      |                                                                                                               |                                                                               |
| 35    |                                                                                                      |                                                                                                               |                                                                               |
| 36    |                                                                                                      |                                                                                                               |                                                                               |
| 37    |                                                                                                      |                                                                                                               |                                                                               |
| 38    |                                                                                                      |                                                                                                               |                                                                               |
| 39    |                                                                                                      |                                                                                                               |                                                                               |

[Conditional Writes - DynamoDB]: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/WorkingWithItems.html#WorkingWithItems.ConditionalUpdate
[Conditional Updates - DynamoDB]: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.ConditionExpressions.html#Expressions.ConditionExpressions.SimpleComparisons
[Handling Duplicate Records - Kenesis]: https://docs.aws.amazon.com/streams/latest/dev/kinesis-record-processor-duplicates.html
[Adding a Single Record - Kenesis]: https://docs.aws.amazon.com/streams/latest/dev/developing-producers-with-sdk.html#kinesis-using-sdk-java-putrecord
[Lambda Concurrency Quotas]: https://docs.aws.amazon.com/lambda/latest/dg/lambda-concurrency.html#concurrency-quotas
[Environment manifest (env.yaml) - Elastic Beanstalk]: https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/environment-cfg-manifest.html
[Advanced environment customization with configuration files (.ebextensions)]: https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/ebextensions.html

## Domain 2: Security

| No   | Q                                                               | A                                                             | Ref |
| ---- | --------------------------------------------------------------- | ------------------------------------------------------------- | --- |
|      |                                                                 |                                                               |     |
| 1    |                                                                 |                                                               |     |
| 2    |                                                                 |                                                               |     |
| 3    |                                                                 |                                                               |     |
| 4    |                                                                 |                                                               |     |
| 5    |                                                                 |                                                               |     |
| 6 ❌ | Provide application in ECS access to the required AWS resources | Fargate: IAM Role -> attach to task                           |     |
|      |                                                                 | EC2: Container Instance Role                                  |     |
| 7 ❌ | KMS: Envelope Encryption                                        | 1. encrypt plaintext data with a data key                     |     |
|      |                                                                 | 2. encrypt the data key with a top-level plaintext master key |     |
| 8    |                                                                 |                                                               |     |
| 9    |                                                                 |                                                               |     |

## Domain 3: Deployment

| No   | Q                                                                              | A                                           | Ref |
| ---- | ------------------------------------------------------------------------------ | ------------------------------------------- | --- |
|      |                                                                                |                                             |     |
| 1    |                                                                                |                                             |     |
| 2    |                                                                                |                                             |     |
| 3    |                                                                                |                                             |     |
| 4    |                                                                                |                                             |     |
| 5 ❌ | CodeDeploy AppSpec - Run a task before traffic is shifted to a Lambda function | AppSpec hook                                |     |
|      |                                                                                | - Lambda: (Before) - AllowTraffic - (After) |     |
| 6    |                                                                                |                                             |     |
| 7    |                                                                                |                                             |     |
| 8    |                                                                                |                                             |     |

## Domain 4: Troubleshooting and Optimization

| No   | Q                                                            | A                                                                         | Ref |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------------------- | --- |
|      |                                                              |                                                                           |     |
| 1    |                                                              |                                                                           |     |
| 2    |                                                              |                                                                           |     |
| 3    |                                                              |                                                                           |     |
| 4    |                                                              |                                                                           |     |
| 5 ❌ | Kinesis Data Streams: Not enough shards & Instances CPU 100% | 1. Increase number of shards (shard splitting). 2. Increase instance size |     |
| 6 ❌ | RDS can't handle read                                        | 1. Use RDS Multi-AZ Cluster (not Multi-AZ Instance)                       |     |
|      |                                                              | 2. Create Read Replica, then update app to read from replica              |     |
| 7 ❌ | X-Ray - namespace, metadata                                  | X-Ray namespace: distinguish `AWS`/`remote`                               |     |
| 8 ❌ | CloudWatch - namespace                                       | CloudWatch namespace: container for metrics, e.g. `aws/lambda`            |     |
| 9    |                                                              |                                                                           |     |
