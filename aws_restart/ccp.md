## Afnan's Notes:
##### <p align="center"> 03/15/23 </p>

Benefits of EC2 over on premise servers in datacenters:
- No upfront cost.
- Doesn't take time to set up and secure datacenters.
- Not locked in or stuck with servers you don't need.
- YOU ONLY PAY FOR WHAT YOU USE.
- Instances are vertically scaleable, can be given more memory and cpu 
when needed.

Multitenancy:
Having independant tenants, or instances which are 
separate from each other but are functioning on 
the same hardware. A good example of this would be 
an apartment building, the tenants are separated 
from each other but still part of one building.

##### <p align="center"> 03/16/23 </p>

With EC2 instances you can either scale UP or scale OUT. 
Scaling up is adding more power to the instances.
While scaling out is to increase the amount of instances.

![Screenshot2023_04_12_153308](https://user-images.githubusercontent.com/124072294/231566198-847dad8c-4093-408a-9ea4-54319d75179b.jpg)


![image](https://user-images.githubusercontent.com/124072294/231566132-9568b42c-97b2-489d-8c46-a261eb200150.png)


### EC2 Auto Scaling:

** Scales horizontally.

<img width="1031" alt="image" 
src="https://user-images.githubusercontent.com/124072294/225665102-00742a04-b2d1-431a-a921-27c8348c8c44.png">

You can also set desired and maximum capacity;
For example, you might configure the Auto Scaling group to scale out in 
response to increased demand, but only to a maximum of four Amazon EC2 
instances.
Again, you pay for only the instances you use, when you use them. 

### Elastic Load Balancing:

Runs on a regional level, automatically and optimally filters traffic to 
multiple recources such as EC2 instances.

It is a single point of contact for all incoming traffic to the previously 
shown auto scaling group. Elastic Load Balancing and Amazon EC2 Auto 
Scaling are separate services, but they work together to help ensure that 
applications running in Amazon EC2 can provide high performance and 
availability. 

<img width="1460" alt="image" 
src="https://user-images.githubusercontent.com/124072294/225673626-5893cad0-7c3b-4457-bc21-aedc47f1f726.png">

Example of decoupled architecture:
<img width="1304" alt="image" 
src="https://user-images.githubusercontent.com/124072294/225679023-8242aa14-2e58-45c6-97d0-59598c0f1492.png">

### Tightly Coupled Architecture vs Loosely Coupled Architecture

A tightly coupled architecture is where applications communicate with each 
other directly. This can have a negative impact in which if one 
application has an error and cannot recieve messages the other application 
will also begin to see errors. (This can be considered as a monolithic 
application.)

A loosely coupled architecture has buffers between applications where they 
are isolated.
If one component fails it won't cause a cascading effect. (While this can 
be considered as a nicroservices approach.)

### Serverless Computing

AWS Serverless cloud computing model allows developers to build and run 
applications and services without worrying about server management. In a 
serverless architecture, the cloud provider, aws in this case, manages the 
infrastructure, scaling, and availability of the servers, and the 
developer only needs to focus on writing code.

AWS Serverless provides a range of services and tools that allow 
developers to create serverless applications, including AWS Lambda, Amazon 
API Gateway etc.

With AWS Serverless, developers can create scalable and highly available 
applications that can handle millions of requests per second without 
worrying about server provisioning, scaling, and availability. 

#### AWS Lambda vs Container Services such as ECS and EKS

AWS Lambda and container services are both serverless computing platforms 
provided by AWS, but they differ in how they manage and run code.

**AWS Lambda:** 
A serverless compute service that allows developers to run code without 
worrying about infrastructure management. It allows developers to write 
code in various programming languages, such as Node.js, Python, Java, Go, 
and more, and execute it in response to events, such as API requests, file 
uploads, and database changes. AWS Lambda automatically scales the compute 
resources to match the incoming request volume and charges only for the 
compute time used.

**AWS Container services suchs as ECS and EKS:**
Container services, on the other hand, are a way to run applications in 
containers that are packaged with all their dependencies and libraries. 
AWS provides container services such as Amazon Elastic Container Service 
(ECS) and Amazon Elastic Kubernetes Service (EKS) that allow developers to 
manage and run containers on a fully managed infrastructure. Container 
services provide more control over the environment in which the 
application runs, making it easier to manage dependencies and 
configurations.

In summary, if you need to run small, independent units of code in 
response to events, then Lambda is the way to go. If you need to run 
full-fledged applications that require more control over the environment 
in which they run, then container services are a better choice.

**AWS Fargate** is a serverless compute engine for containers that allows 
you to run Docker containers in the cloud without managing underlying 
infrastructure. Fargate is designed to simplify the deployment and 
management of containerized applications, allowing you to focus on 
building and running your applications rather than managing 
infrastructure. With Fargate, you don't need to provision or manage 
servers, which means you can avoid the overhead of capacity planning, 
patching, and maintenance.

>#### Differences between AWS Fargate, ECS and EKS:
>
>> **AWS Fargate** Fargate manages the infrastructure required to run your 
containers, such as virtual machines, and automatically scales the 
infrastructure based on your application's needs. With Fargate, you only 
pay for the compute resources consumed by your application.
>
>> **Amazon Elastic Container Service (ECS)** is a container management 
service that allows you to run Docker containers on a managed cluster of 
EC2 instances. You are responsible for managing the EC2 instances, but ECS 
automates the management of the container orchestration, load balancing, 
and scaling. You can run ECS on either a cluster of EC2 instances or on 
Fargate.
>
>> **Amazon Elastic Kubernetes Service (EKS)** is a fully managed 
Kubernetes service that allows you to run Kubernetes clusters on AWS 
without having to manage the underlying infrastructure. EKS simplifies the 
deployment, scaling, and management of Kubernetes applications and 
provides a highly available and secure environment. EKS is based on the 
open-source Kubernetes project and is fully compatible with Kubernetes 
tooling and APIs.

##### <p align="center"> 03/18/21 </p>

### AWS High Availability and Fault Tolerance.
#### AWS Regions
-  AWS builds **regions** closest to where business traffic demands.
- Locations sucs as Paris, Tokyo, Ohio
- Each reagion has multiple data centers.
- THey are connected with high speed fiber network.
- Each reagion is isolated from other regions, data doesn't flow through 
them unless they are explicitly told to do so.
- This is called regioal data soverignty.
- Pricing varies depending on regions.

#### AWS Availability Zones
- One or more discrete data centers. 
- Spread out in the region.

<img width="1095" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226136387-e3b3e111-e05a-4aa5-b27b-aecd5dcfee0e.png">

#### Edge Locations
An edge location is a site that Amazon CloudFront uses to store cached 
copies of your content closer to your customers for faster delivery.

<img width="904" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226137936-cc80d551-7249-4620-84f4-ff01940bf647.png">


**AWS Cloudfront**
- CDN = Content Delivery Network
- Used to cache date. Providing low latency to customers.
- Uses edge locations.


**Amazon Route 53**
- DNS = Domain Name Servie
- Used to route customers to correct web locations with low latency
- You can also buy domain names and manage them directly on AWS using 
Route 53.
**AWS Outposts**
- AWS Outposts is a service that allows customers to run AWS 
infrastructure and services on-premises or in a co-location facility. 

### API : Application programming interface
- These Api's are invoked to interact with AWS services.

This can be done with:
- AWS Management Console
- AWS Command Line Interface CLI
- AWS Software Development Kits SDKs

**AWS Elastic Beanstalk**

Platform as a Service (PaaS)

With AWS Elastic Beanstalk, you provide code and configuration settings, 
and Elastic Beanstalk deploys the resources necessary to perform the 
following tasks:
- Adjust capacity
- Load balancing
- Automatic scaling
- Application health monitoring

**AWS Cloud Formation**

Infrastructure as Code (IaC)

<img width="1391" alt="image" src="https://user-images.githubusercontent.com/124072294/230260893-b7eccb13-647f-4b9b-a2ed-2cec990e5bb8.png">

**AWS SDK is used to interact with AWS services programmatically, while IAC tools such as AWS CloudFormation and AWS CDK are used to define and deploy infrastructure resources on AWS in a repeatable and automated fashion.


Allows you to define what you want in a cloud formation template in 
formats like JSON or YAML and AWS CloudFormation parses the document and 
begins to provision all the resources that were defined.

Manages all the calles to the backend APIS.


**In summary** both Elastic Beanstalk and CloudFormation help you deploy 
and manage applications on AWS, but they have different approaches and use 
cases. Elastic Beanstalk is focused on application deployment and 
management, while CloudFormation is focused on infrastructure provisioning 
and management.

### Amazon Virtual Private Cloud
### Security Groups vs Network Access Control List
<img width="1920" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226146097-a47f430c-b0b8-4d3c-859b-0d960c505e54.png">

**Stateful** They are stateful, meaning that any inbound traffic that is 
allowed is automatically permitted to flow outbound, and vice versa.
Denies all inbound traffic by default.
**Stateless** meaning hey are stateless, meaning that they evaluate each 
incoming and outgoing packet independently based on the rules, and they 
can be applied to multiple subnets within a VPC.
Allows all inbound and out bound traffic by default.


**Amazon CloudFront**

Amazon CloudFront is a content delivery network (CDN) service offered by 
Amazon Web Services (AWS) that delivers content, videos, applications, and 
APIs to end-users with low latency and high transfer speeds.

CloudFront uses a global network of edge locations that cache content 
closer to the end-users, reducing the time it takes to load web pages and 
other content. When a user requests a file from a CloudFront distribution, 
the request is automatically routed to the nearest edge location, which 
then serves the file directly from the cache if it's available.

A CloudFront distribution is a collection of edge locations that cache 
copies of your content to improve delivery speed and reduce latency for 
end-users. When you create a CloudFront distribution, you specify the 
origin for the content that you want to deliver, which can be an S3 
bucket, an EC2 instance, or a load balancer, among other options.

### Database and Storage.
**Amazon Elastic Block Storage EBS**
<img width="1012" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226147133-cc915c83-9d34-47f3-bfeb-39af8cd39c5a.png">

<img width="1093" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226147148-ea07eae6-54c7-401d-8ea8-6ebd45f1c98f.png">

**Amazon Elastic Block Store (EBS)** is a block storage service that 
provides highly available and reliable storage volumes for use with Amazon 
EC2 instances. Amazon EBS Snapshots are point-in-time copies of an EBS 
volume, which can be used for backup, disaster recovery, or to migrate 
data between Amazon Web Services (AWS) regions.

Needs to be in the same availabilty zone as the EC2 instances to attach to 
them.
Volume does not automatically scale.

An **Amazon EBS snapshot** contains all the data on the volume since the 
last snapshot, and not just the changes. Snapshots are incremental, 
meaning that only the data that has changed since the last snapshot is 
saved. This can help save storage space and reduce costs.

**Amazon Elastic File System EFS**
- Each time you read or write you have to pay while using EFS.
- EFS can be used to create and manage file systems that can be accessed 
by multiple instances simultaneously.
-  EFS supports the NFS protocol and can be accessed by instances in 
multiple Availability Zones within the same region. Is a regional 
resource.
- Linux file system.
- Automatically scales as you write to it. 
### AWS S3 Bucket

<img width="626" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226150756-a64ab481-f90b-43b2-b35f-4917b3bd94ba.png">

<img width="1917" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226152852-79d60b93-5e05-48ba-82da-ca06f583af2b.png">

<img width="1918" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226152869-95b1da9e-2b09-4665-b7fc-874a427e8c51.png">


**Amazon S3 Standard**
Comes with 11 9's of durability.
Data stored in atleast 3 facilities.

**Amazon S3 Static website hosting**

**Amazon S3 Standard - Infrequent Access (S3 Standard IA)**

Good for data that requires long term storage but also quick access when 
needed.

**Amazon S3 Intelligent-Tiering**

Ideal for data with unknown or changing access patterns
Requires a small monthly monitoring and automation fee per object
In the Amazon S3 Intelligent-Tiering storage class, Amazon S3 monitors 
objects’ access patterns. If you haven’t accessed an object for 30 
consecutive days, Amazon S3 automatically moves it to the infrequent 
access tier, Amazon S3 Standard-IA. If you access an object in the 
infrequent access tier, Amazon S3 automatically moves it to the frequent 
access tier, Amazon S3 Standard.

**Amazon S3 Glacier**
Used to archive data

**Amazon S3 Lifecycle policy** 
Can move files in between different tiers automatically depending on your 
configurations.

<img width="798" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226705767-b83055f6-af52-4508-87e0-c59cca9d8bb9.png">

##### <p align="center"> 03/19/23 </p>

### Amazon Relational Database Service

**(Amazon RDS)**: 

<img width="1918" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226208874-242c8b38-da68-4d47-af01-8823a5038016.png">

- Automated Patching
- Backups
- Redundancy
- Failover
- Disaster recovery

Data Stoerd such that it relates to other pieces of data.
Lift and shift migration 
have access to save variable as on premise.

**Amazon Aurora**
- 1/10th the price of commercial databases
- Data is replicated, you have 6 copies at any given time
- Up to 15 read replicas
- Continuous backup to Amazon S3
- Can scale up to 128 TB of storage

Consider Amazon Aurora if your workloads require high availability. It 
replicates six copies of your data across three Availability Zones and 
continuously backs up your data to Amazon S3.

**Amazon Dynamo DM**
- Serverless
- Non Relational Database / NoSQL Database

<img width="1920" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226208905-f887d421-114f-4664-b7e8-b868e6bee7b9.png">

**Amazon Redshift**
- Data warehouse

### Data Migration

**Amazon Data Migtation Service DMS**

Migrate data securely.
Source database remains fully operational.


### AWS shared responsibility model

<img width="1918" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226210730-fc53a4d0-85b7-4d40-89bc-8aafa048656b.png">

<img width="1916" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226214960-d8c72a58-b737-4677-809c-e2eb7531ee8e.png">

<img width="905" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226215025-0d9b7f26-4d00-423c-b158-9c2d06aa1837.png">


### IAM

Example of a IAM Policy:
<img width="1245" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226215244-a22807d1-70f9-4a77-854c-8f6adce4d6b4.png">

- Effect is always either Allow or Deny
- Action can be any API call
- Resource is which specific AWS resource that API call is for

**IAM Security Tools**

*• IAM Credentials Report (account-level)*

• a report that lists all your account's users and the status of their various
credentials

*• IAM Access Advisor (user-level)*

• Access advisor shows the service permissions granted to a user and when those
services were last accessed.
• You can use this information to revise your policies.

##### <p align="center"> 03/20/23 </p>

**AWS Key Management Service AWS KMS**

- enables you to perform encryption operations through the use of 
cryptographic keys.

**AWS Artifact**
Security and Compliace related service.
**AWS Sheild**

**Amazon Inspector**
Amazon Inspector helps to improve the security and compliance of 
applications by running automated security assessments. It checks 
applications for security vulnerabilities and deviations from security 
best practices, such as open access to Amazon EC2 instances and 
installations of vulnerable software versions. 

After Amazon Inspector has performed an assessment, it provides you with a 
list of security findings. The list prioritizes by severity level, 
including a detailed description of each security issue and a 
recommendation for how to fix it. However, AWS does not guarantee that 
following the provided recommendations resolves every potential security 
issue. Under the shared responsibility model, customers are responsible 
for the security of their applications, processes, and tools that run on 
AWS services.

**Amazon GuardDuty**

<img width="994" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226431921-7f4fa312-ce9a-443d-b8ea-89067530f95d.png">

After you have enabled GuardDuty for your AWS account, GuardDuty begins 
monitoring your network and account activity. You do not have to deploy or 
manage any additional security software. GuardDuty then continuously 
analyzes data from multiple AWS sources, including VPC Flow Logs and DNS 
logs. 

If GuardDuty detects any threats, you can review detailed findings about 
them from the AWS Management Console. Findings include recommended steps 
for remediation. You can also configure AWS Lambda functions to take 
remediation steps automatically in response to GuardDuty’s security 
findings.

### Monitoring

Observing systems, collecting metrics, evaluating data to make decisons or 
take actions is called monitoring.

**Amazon CloudWatch**

Amazon CloudWatch is a web service that enables you to monitor and manage 
various metrics and configure alarm actions based on data from those 
metrics.

CloudWatch uses metrics to represent the data points for your resources. 
AWS services send metrics to CloudWatch. CloudWatch then uses these 
metrics to create graphs automatically that show how performance has 
changed over time. 

>CloudWatch alarms
>
>With CloudWatch, you can create alarms that automatically perform actions 
if the value of your metric has gone above or below a predefined 
threshold. 
>
>For example, suppose that your company’s developers use Amazon EC2 
instances for application development or testing purposes. If the 
developers occasionally forget to stop the instances, the instances will 
continue to run and incur charges. 
>
>In this scenario, you could create a CloudWatch alarm that automatically 
stops an Amazon EC2 instance when the CPU utilization percentage has 
remained below a certain threshold for a specified period. When 
configuring the alarm, you can specify to receive a notification whenever 
this alarm is triggered.


**AWS CloudTrail**

The comprehensive API auditing tool. The engine is simple, every request 
made to AWS, it doesn't matter if it's to launch an EC2 instance, or add a 
row to a DynamoDB table, or change a user's permissions. Every request 
gets logged in the CloudTrail engine. The engine records exactly who made 
the request, which operator, when did they send the API call? Where were 
they? What was their IP address? And what was the response? Did something 
change? And what is the new state? Was the request denied? 


**AWS Trusted Advison**

AWS Trusted Advisor is a web service that inspects your AWS environment 
and provides real-time recommendations in accordance with AWS best 
practices.

Trusted Advisor compares its findings to AWS best practices in five 
categories: 

1 cost optimization 
2 performance
3 security
4 fault tolerance
5 service limits 

For the checks in each category, Trusted Advisor offers a list of 
recommended actions and additional resources to learn more about AWS best 
practices. 


**AWS Snowmobile** is a data transfer service that uses a secure, 
ruggedized shipping container to transfer up to 100PB of data between 
on-premises data centers and AWS. It is typically used when organizations 
need to transfer large amounts of data over long distances, and when 
network-based transfers are not feasible due to bandwidth limitations, 
security concerns, or other factors.

**Snowball** is a smaller, portable data transfer device that can be used 
to transfer up to 80TB of data between on-premises data centers and AWS. 
It is designed to be secure, with encryption used to protect data both in 
transit and at rest, and is typically used when organizations need to 
transfer large amounts of data more quickly than they could over a network 
connection, or when they need to transfer data to or from locations with 
limited or no network connectivity.

### AWS Free Tier

Three types of offers are available: 

- Always Free

For example AWS Lambda 1 million free invocation per month, and it doesn't 
expire.

- 12 Months Free

Amazon S3 free for 12 months for up to 5GB of storage.

- Trials

AWS Lightsail offers 1 month trial of up to 750 hours of usage.

These only scratch the surface.

**AWS Consolidated Billing**

**Free Feature

At the end of every month, instead of having to pay an AWS bill for every 
single account, you can roll those bills up into one bill owned by the 
owner of the organization. This makes it easier to keep track of your 
bills. You don't get 100 bills, if you have 100 AWS accounts.

There are other benefits of using this feature too. One of them is that 
the usage for AWS resources is rolled up to the organization level. AWS 
does offer bulk pricing. Each individual account may only have a small 
amount of usage, but you can get the bulk discount pricing because of the 
aggregate across all accounts in the organization. 

In addition, if you have a savings plan in place, or if you are using 
reserved instances for EC2, it can be shared across AWS accounts in the 
organization.

**AWS Budgets**

In AWS Budgets, you can create budgets to plan your service usage, service 
costs, and instance reservations.

The information in AWS Budgets updates three times a day. This helps you 
to accurately determine how close your usage is to your budgeted amounts 
or to the AWS Free Tier limits.

In AWS Budgets, you can also set custom alerts when your usage exceeds (or 
is forecasted to exceed) the budgeted amount.

<img width="494" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226722422-c3de2243-1d2b-4f7c-9699-a9390db99153.png">


### AWS Support

**Basic Support** is free for all AWS customers. It includes access to 
whitepapers, documentation, and support communities. With Basic Support, 
you can also contact AWS for billing questions and service limit 
increases.

With Basic Support, you have access to a limited selection of AWS Trusted 
Advisor checks. Additionally, you can use the AWS Personal Health 
Dashboard, a tool that provides alerts and remediation guidance when AWS 
is experiencing events that may affect you. 

<img width="1805" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226716727-ee96577f-e586-467f-98df-8c6dae9c530f.png">

### The AWS Well-Architected Framework

The AWS Well-Architected Framework helps you understand how to design and 
operate reliable, secure, efficient, and cost-effective systems in the AWS 
Cloud. It provides a way for you to consistently measure your architecture 
against best practices and design principles and identify areas for 
improvement.

<img width="805" alt="image" 
src="https://user-images.githubusercontent.com/124072294/226758922-6d92a9eb-5a91-4a1e-ae5a-11d8c20b794f.png">

Look into Cloud adoption framework


**The 5 Pillars of the AWS Well-Architected Framework:**
    
1- Operational Excellence: The operational excellence pillar includes the ability to run and monitor systems to deliver business value and to continually improve supporting processes and procedures.

2- Security: The security pillar includes the ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies.

3- Reliability: The reliability pillar includes the ability of a system to recover from infrastructure or service disruptions, dynamically acquire computing resources to meet demand, and mitigate disruptions such as  misconfigurations or transient network issues.

4- Performance Efficiency: The performance efficiency pillar includes the ability to use computing resources efficiently to meet system requirements and to maintain that efficiency as demand changes and technologies evolve.

5- Cost Optimization: The cost optimization pillar includes the ability to avoid or eliminate unneeded cost or sub-optimal resources.


### Amazon Macie

Amazon Macie is a fully managed security service that uses machine learning and pattern matching techniques to automatically discover, classify, and protect sensitive data in AWS. It can identify sensitive data such as personally identifiable information (PII), intellectual property, and financial data, and provide alerts and recommendations on how to secure the data. Macie provides a dashboard that allows you to see an inventory of your sensitive data and view alerts, including those related to non-compliant data access attempts. It also provides a continuous monitoring feature that can detect new sensitive data as it is created, and integrates with other AWS services such as Amazon S3 and AWS CloudTrail.

### AWS Storage Gateway 
 
A hybrid cloud storage service that provides on-premises applications with access to virtually unlimited cloud storage. It enables hybrid storage between on-premises storage environments and AWS storage services, including Amazon S3, Amazon S3 Glacier, Amazon EBS, and Amazon DynamoDB. AWS Storage Gateway is deployed as a virtual machine or a hardware appliance in the customer's data center, and it can store data in the cloud for scalable and cost-effective storage. It also provides features such as data transfer, backup and restore, disaster recovery, and caching to improve performance and reduce the latency of accessing cloud storage.


### Support Plans

![image](https://user-images.githubusercontent.com/124072294/231270790-8707fec9-aa97-4d69-9b35-c9401787e35e.png)

<img width="406" alt="image" src="https://user-images.githubusercontent.com/124072294/231496800-d20ecc0e-6dcb-4794-8ca0-c9a45a9ee8c5.png">

### Similar Yet Different

**CloudWatch Logs and CloudTrail** are both AWS services that are used for monitoring and logging. However, they differ in their primary use cases and functionalities.

CloudWatch Logs is a logging service that allows you to monitor, store, and access log files from AWS resources like EC2 instances, Lambda functions, and VPC Flow Logs.

On the other hand, CloudTrail is an AWS service that provides a record of events and API calls made within your AWS account. It captures information about who made the call, what service was called, what parameters were used, and when the call was made.

In summary, CloudWatch Logs is primarily used for monitoring and analyzing logs from AWS resources, while CloudTrail is used for auditing and tracking changes made to your AWS account.

**CloudWatch and CloudWatch Logs**
CloudWatch is a monitoring service that provides metrics and log data about AWS resources, applications, and services. CloudWatch Logs is a service that helps you monitor, store, and access log files from multiple sources in a central location.