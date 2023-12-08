# Tutorial Dojo - DVA-C02 - Timed Mode Set 4

Test time: Dec 8 2023, 10h00 - 10h50 (00:50:00)

Score: 60/65 (92.3%):

- CDA – Development with AWS Services 91.67% (33/36)
- CDA – Security 90.91% (10/11)
- CDA – Deployment 80% (4/5)
- CDA – Troubleshooting and Optimization 100% (13/13)

## Domain 1: Development with AWS Services

| No  |     | Q                                                                                           | A                                                                                 | Ref |
| --- | --- | ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --- |
|     |     |                                                                                             |                                                                                   |     |
| 1   | ✅  |                                                                                             |                                                                                   |     |
| 2   | ✅  |                                                                                             |                                                                                   |     |
| 3   | ✅  |                                                                                             |                                                                                   |     |
| 4   | ✅  |                                                                                             |                                                                                   |     |
| 5   | ✅  |                                                                                             |                                                                                   |     |
| 6   | ✅  |                                                                                             |                                                                                   |     |
| 7   | ✅  |                                                                                             |                                                                                   |     |
| 8   | ❌  | DynamoDB - GSI: Consumed throughput; Consistency?                                           | GSI has its own consumed throughput. GSI only supports eventually consistent read |     |
| 9   | ✅  |                                                                                             |                                                                                   |     |
| 10  | ✅  |                                                                                             |                                                                                   |     |
| 11  | ✅  |                                                                                             |                                                                                   |     |
| 12  | ✅  |                                                                                             |                                                                                   |     |
| 13  | ✅  |                                                                                             |                                                                                   |     |
| 14  | ✅  |                                                                                             |                                                                                   |     |
| 15  | ❌  | ECS: Tasks are scheduled on instances with enough resources. Which task placement strategy? | Random                                                                            |     |
| 16  | ✅  |                                                                                             |                                                                                   |     |
| 17  | ✅  |                                                                                             |                                                                                   |     |
| 18  | ✅  |                                                                                             |                                                                                   |     |
| 19  | ✅  |                                                                                             |                                                                                   |     |
| 20  | ✅  |                                                                                             |                                                                                   |     |
| 20  | ✅  |                                                                                             |                                                                                   |     |
| 21  | ✅  |                                                                                             |                                                                                   |     |
| 22  | ✅  |                                                                                             |                                                                                   |     |
| 23  | ✅  |                                                                                             |                                                                                   |     |
| 24  | ✅  |                                                                                             |                                                                                   |     |
| 25  | ✅  |                                                                                             |                                                                                   |     |
| 26  | ✅  |                                                                                             |                                                                                   |     |
| 27  | ✅  |                                                                                             |                                                                                   |     |
| 28  | ✅  |                                                                                             |                                                                                   |     |
| 29  | ✅  |                                                                                             |                                                                                   |     |
| 30  | ✅  |                                                                                             |                                                                                   |     |
| 20  | ✅  |                                                                                             |                                                                                   |     |
| 21  | ✅  |                                                                                             |                                                                                   |     |
| 22  | ✅  |                                                                                             |                                                                                   |     |
| 23  | ✅  |                                                                                             |                                                                                   |     |
| 24  | ✅  |                                                                                             |                                                                                   |     |
| 25  | ✅  |                                                                                             |                                                                                   |     |
| 26  | ✅  |                                                                                             |                                                                                   |     |
| 27  | ✅  |                                                                                             |                                                                                   |     |
| 28  | ✅  |                                                                                             |                                                                                   |     |
| 29  | ✅  |                                                                                             |                                                                                   |     |
| 30  | ✅  |                                                                                             |                                                                                   |     |
| 31  | ✅  |                                                                                             |                                                                                   |     |
| 32  | ✅  |                                                                                             |                                                                                   |     |
| 33  | ❌  | Deploy containerized apps? ECS, EKS or Elastic Beanstalk?                                   | Under the hood, Elastic Beanstalk uses ECS (& ELB, ASG)                           |     |
| 34  | ✅  |                                                                                             |                                                                                   |     |
| 35  | ✅  |                                                                                             |                                                                                   |     |
| 36  | ✅  |                                                                                             |                                                                                   |     |

## Domain 2: Security

| No  |     | Q                                                                    | A                                     | Ref |
| --- | --- | -------------------------------------------------------------------- | ------------------------------------- | --- |
|     |     |                                                                      |                                       |     |
| 1   | ❌  | 1 bucket - many users. How to redact PII & manage access permission? | Use S3 Object Lambda (+) Access Point |     |
| 2   | ✅  |                                                                      |                                       |     |
| 3   | ✅  |                                                                      |                                       |     |
| 4   | ✅  |                                                                      |                                       |     |
| 5   | ✅  |                                                                      |                                       |     |
| 6   | ✅  |                                                                      |                                       |     |
| 7   | ✅  |                                                                      |                                       |     |
| 8   | ✅  |                                                                      |                                       |     |
| 9   | ✅  |                                                                      |                                       |     |
| 10  | ✅  |                                                                      |                                       |     |
| 11  | ✅  |                                                                      |                                       |     |

### 2.1 S3 Object Lambda

## Domain 3: Deployment

| No  |     | Q                                       | A                                                                              | Ref |
| --- | --- | --------------------------------------- | ------------------------------------------------------------------------------ | --- |
|     |     |                                         |                                                                                |     |
| 1   | ❌  | SAM deploy process (From local machine) | 1. Build (local); 2. Package ("Publish" to S3); 3. Deploy (Use artifact on S3) |     |
| 2   | ✅  |                                         |                                                                                |     |
| 3   | ✅  |                                         |                                                                                |     |
| 4   | ✅  |                                         |                                                                                |     |
| 5   | ✅  |                                         |                                                                                |     |

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

- https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-deploying.html

## Domain 4: Troubleshooting and Optimization

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   | ✅  |     |     |     |
| 2   | ✅  |     |     |     |
| 3   | ✅  |     |     |     |
| 4   | ✅  |     |     |     |
| 5   | ✅  |     |     |     |
| 6   | ✅  |     |     |     |
| 7   | ✅  |     |     |     |
| 8   | ✅  |     |     |     |
| 9   | ✅  |     |     |     |
| 10  | ✅  |     |     |     |
| 11  | ✅  |     |     |     |
| 12  | ✅  |     |     |     |
| 13  | ✅  |     |     |     |
