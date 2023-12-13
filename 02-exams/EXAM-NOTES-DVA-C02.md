# Exam note AWS DVA-C03

## Queue/stream retention time

| Queue                       | Min | Retention time<br>(Default) | Max      | Note                                              |
| --------------------------- | --- | --------------------------- | -------- | ------------------------------------------------- |
| SQS queue                   | 60s | 4 days                      | 14 days  | No addition charging                              |
| Kinesis Data Streams stream | 24h | 24h (One-day retention)     | 365 days | **Extended** data retention: up to 7 days 💸      |
|                             |     |                             |          | **Long-term** data retention: up to 365 days 💸💸 |
| DB Streams queue            | -   | 24h                         | -        | Can't be changed                                  |

[Message lifecycle - SQS]: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-basic-architecture.html#sqs-message-lifecycle
[Changing the Data Retention Period - Kinesis Data Streams]: https://docs.aws.amazon.com/streams/latest/dev/kinesis-extended-retention.html
[Data retention limit for DynamoDB Streams]: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html#Streams.DataRetention

## Deployment strategy

### 3.2 Elastic Beanstalk Deployment policies

- Deployment policies (aka deployment methods/strategies):
  - AllAtOnce (Default)
  - Rolling
  - Rolling with additional batch
  - Immutable
  - Traffic splitting (aka Canary)
  - Blue-green (with `Swap environment URLs`)

[3.2.1]: https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.deploy-existing-version.html
[3.2.2]: https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.rolling-version-deploy.html
[3.2.3]: https://docs.aws.amazon.com/whitepapers/latest/introduction-devops-aws/aeb-deployment-strategies.html

### 3.6 CodeDeploy deployment type

[Overview of CodeDeploy deployment types](https://docs.aws.amazon.com/codedeploy/latest/userguide/welcome.html#welcome-deployment-overview)
[CodeDeploy concepts](https://docs.aws.amazon.com/codedeploy/latest/userguide/primary-components.html#primary-components-deployment-type)

CodeDeploy can deploy application to 3 platform (called **deployment platform**):

- EC2/On-Premises <= Needs CodeDeploy agent
- ECS
- Lambda

CodeDeploy make the latest application _revision_ available on instance in a **deployment group** (a group of instances)

- In-place deployment: only support EC2/On-Premise
- Blue/green deployment

CodeDeploy supports 3 ways of routing traffic (via **deployment configuration**)

- All-at-once: 100%
- Canary: 2 increments: 10% + 90%
- Linear: n% x m times
