# Notes for AWS CCP

##### 03/15/23

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

##### 03/16/23

With EC2 instances you can either scale UP or scale OUT. 
Scaling up is adding more power to the instances.
While scaling out is to increase the amount of instances.

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

