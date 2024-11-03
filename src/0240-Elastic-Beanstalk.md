# Elastic Beanstalk In-Depth

## Elastic Beanstalk (EB) - Architecture (18:12)

![Alt text](<images/Screenshot from 2023-12-04 09-46-00.png>)
Elastic Beanstalk (EB): Overview

> [!NOTE] What is Elastic Beanstalk (EL)?
> Elastic Beanstalk is a Platform as a service (PaaS)
>
> - Developers provides code
> - EB handles the deployment
>
>   - capacity provisioning
>   - load balancing
>   - automatic scaling to web application health monitoring,
>   - with ongoing fully managed patch and security updates
>   - and many other things
>     - networking (VPC, subnets)
>     - EC2 instance: EBS, CloudWatch, Security Group
>     - database
>     - deployment strategy...

![Alt text](<images/Screenshot from 2023-12-04 09-47-57.png>)
Elastic Beanstalk (EB): Platforms

> [!NOTE]
> EB provides:
>
> - _Managed Platform_ for many languages:
>   - Go, Java,
>   - .NET, .NET Code,
>   - Node, PHP, Python, Ruby
> - _Custom Platform_ via Docker

![Alt text](<images/Screenshot from 2023-12-04 09-55-49.png>)
Elastic Beanstalk (EB): Architecture

> [!NOTE] How to use EB?
> When working with EB, you:
>
> 1. Create an EB _application_
> 2. Bundle a deployable code (aka _source bundle_) as an _application version_ that will be automatically deployed either as
>    One of two type of Environment tier:
>    - _Web Server environment_
>    - a _Worker environment_, that can be deployed with a message queue (SQS)
> 3. Manage the environments
> 4. Update new application version, and EB will deploy new versions of environments

![Alt text](<images/Screenshot from 2023-12-04 09-57-18.png>)
Elastic Beanstalk (EB): Blue-Green Deployment

![Alt text](<images/Screenshot from 2023-12-04 10-01-26.png>)
Elastic Beanstalk (EB): Summary

## [DEMO] Elastic Beanstalk (EB) - Application & Environment - PART1 (11:50)

## [DEMO] Elastic Beanstalk (EB) - Add additional environment and config options - PART2 (10:53)

## Elastic Beanstalk (EB) - Deployment Policies (11:40)

![Alt text](<images/Screenshot from 2023-12-04 10-46-47.png>)
EB - Deployment Policies

![Alt text](<images/Screenshot from 2023-12-04 10-48-42.png>)
EB - Deployment Policies: All at once

![Alt text](<images/Screenshot from 2023-12-04 10-50-13.png>)
EB - Deployment Policies: Rolling

![Alt text](<images/Screenshot from 2023-12-04 10-51-55.png>)
EB - Deployment Policies: Rolling with additional batch

![Alt text](<images/Screenshot from 2023-12-04 10-55-38.png>)
EB - Deployment Policies: Immutable

![Alt text](<images/Screenshot from 2023-12-04 10-56-26.png>)
EB - Deployment Policies: Traffic Splitting

![Alt text](<images/Screenshot from 2023-12-04 10-56-48.png>)
EB & Blue-Green Deployment

## [DEMO] Elastic Beanstalk (EB) - Deployment (8:30)

## Elastic Beanstalk (EB) - Environments and RDS (4:34)

![Alt text](<images/Screenshot from 2023-12-04 11-09-51.png>)

![Alt text](<images/Screenshot from 2023-12-04 11-10-19.png>)

![Alt text](<images/Screenshot from 2023-12-04 11-11-24.png>)

## Elastic Beanstalk (EB) - Advanced Customization via .ebextensions (4:52)

![Alt text](<images/Screenshot from 2023-12-04 11-35-52.png>)

> [!NOTE] Elastic Beanstalk is based on CloudFormation>
>
> Use can provide additional Cfn configuration via the `.config` files inside `.ebextensions` folder in the source bundle.
>
> These config can:
>
> - modify the EB application environment
> - modify the EC2 instances
> - deploy custom Cfn resources, make advance modification to Cfn resources
> - ...
>
> See [GitHub - awsdocs/elastic-beanstalk-samples](https://github.com/awsdocs/elastic-beanstalk-samples)

## Elastic Beanstalk (EB) - HTTPS (1:51)

![Alt text](<images/Screenshot from 2023-12-04 11-40-28.png>)

## Elastic Beanstalk (EB) - Cloning (4:44)

![Alt text](<images/Screenshot from 2023-12-04 11-43-47.png>)

## Elastic Beanstalk (EB) - Docker (9:11)

![Alt text](<images/Screenshot from 2023-12-04 11-48-27.png>)

![Alt text](<images/Screenshot from 2023-12-04 11-50-32.png>)

![Alt text](<images/Screenshot from 2023-12-04 11-51-50.png>)

## [DEMO] Elastic Beanstalk (EB) - Section Cleanup (1:40)

## Section Quiz - Elastic Beanstalk
