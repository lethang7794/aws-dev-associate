# Exam note AWS DVA-C03

## Queue/stream retention time

| Queue                       | Min | Retention time<br>(Default) | Max      | Note                                              |
| --------------------------- | --- | --------------------------- | -------- | ------------------------------------------------- |
| SQS queue                   | 60s | 4 days                      | 14 days  | No addition charging                              |
| Kinesis Data Streams stream | 24h | 24h (One-day retention)     | 365 days | **Extended** data retention: up to 7 days 💸      |
|                             |     |                             |          | **Long-term** data retention: up to 365 days 💸💸 |
| DB Streams queue            | -   | 24h                         | -        | Can't be changed                                  |

- Message lifecycle - SQS: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-basic-architecture.html#sqs-message-lifecycle
- Changing the Data Retention Period - Kinesis Data Streams: https://docs.aws.amazon.com/streams/latest/dev/kinesis-extended-retention.html
- Data retention limit for DynamoDB Streams: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html#Streams.DataRetention
