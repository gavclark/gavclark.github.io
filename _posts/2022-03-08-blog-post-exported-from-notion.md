# AWS Cloud Practitioner

---

## Topic: What is Cloud Computing

### Recall

What is the definition of cloud computing

What is virtualization?

What is a hypervisor

### Notes

- Remote virtual pool on on-demand shared resources offering Compute, Storage, Database and Network services that can be rapidly deployed at scale
- it allows the possibility of having multiple **virtual machines (VMs)** , each running essentially a separate operating system and applications, installed on 1 physical server
- Shared hardware is achieved through a hypervisor. It is a piece of software used to create the virtualized environment allowing multiple VMs on the same host. The hypervisor sits between the physical hardware and the VMs

<aside>
📌 **SUMMARY: How Data Center Architecture is reflected in the cloud:** [https://aws.amazon.com/compliance/ ,](https://aws.amazon.com/compliance/) [https://www.microsoft.com/en-us/trust-center/compliance/compliance-overview](https://www.microsoft.com/en-us/trust-center/compliance/compliance-overview) , [https://aws.amazon.com/products/storage/](https://aws.amazon.com/products/storage/) , [https://azure.microsoft.com/en-us/product-categories/storage/](https://azure.microsoft.com/en-us/product-categories/storage/)

</aside>

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled.png)

<aside>
💡 before fully understanding cloud computing we must be aware of some of the existing technology that it is based on. Virtualization has been used in on-premise datacenters for a long time

</aside>

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%201.png)

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%202.png)

## Topic: Cloud Deployment Models

### Recall

Name the three different cloud model types

### Notes

- Public Cloud, Private Cloud, Hybrid Cloud
- ...

<aside>
📌 **SUMMARY: Public cloud model is where a vendor makes available the use of shared infrastructure (compute, storage, database, network) . it can be provisioned on demand and typically accessed over the internet for usage. Private Cloud is different to public cloud in that the infrastructure is privately hosted, managed and owned by the company using it. Hybrid cloud is a model that makes use of both Public and Private models.  A hybrid model is established when a network link is configured between the Private Cloud to services within the Public Cloud**

</aside>

---

## Topic: Key Cloud Concepts

- **On-demand resourcing** - when you want to provision a resource within the Cloud it is almost immediately available to you , where and when you need it
- **Scalability** - offers the ability to rapidly scale your environments resources both ‘up and down’ (scale up) and ‘in and out’ (scale out)
- **Economy of scale**  - the huge scale of resources public cloud offers provide an exceptionally low resource cost compared to traditional hosting
- **Flexibility & Elasticity -** you choose the amount of resources you require, how much and how long you want it and at what scale. You can fully customize your environment
- **Growth** - cloud computing offers your organization the ability to grow using a wide range of resources and services. Growth constraints are significantly reduced compared to a classic environment
- **Utility Based Metering**  - with most cloud services, you only pay for what you use
- **Shared Infrastructure -** hosts in the cloud are virtualized and as a result multiple tenants (organisations/users) can be running VMs on the same hardware. Significantly reduces physical hardware required
- **Highly Available** - many of the core services in Public Cloud and underlying infrastructure are replicated across different geographic zones and regions. Having these services and data in multiple places ensures durability and availability, increasing g the resilience.
- **Security** - Many enterprises still have concerns over how secure public cloud computing is. However, public cloud vendors like AWS and Azure are considered more secure than your own datacenter as they need to adhere to global regulatory compliance across multiple industries and geographies

## **Topic: Cloud Service Models**

- Infrastructure as a Service (IaaS)
- Platform as a Service (PaaS)
- Software as a Service (SaaS)

### Recall

Name the 3 Cloud Service Models

### Notes

- Infrastructure as a Service (IaaS)
- Platform as a Service (PaaS)
- Software as a Service (SaaS)

---

## Topic: Common use cases of Cloud Computing

- Migration of production workloads to cloud
- Traffic bursting - seasonal increase in compute, storage etc.
- Backup and DR
- Web hosting
- Test & Development environments
- Proof of Concept
- Big data - analytics - AI

---

## Topic - How Data Center architecture is reflected into the cloud

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%203.png)

<aside>
📌 **SUMMARY:**

</aside>

---

## Topic: Compute Fundamentals for AWS

[https://aws.amazon.com/products/compute/](https://aws.amazon.com/products/compute/)

Elastic Compute Cloud (EC2)

Amazon ECS (EC2 Container Service)

Amazon ECR (Elastic Container Registry)

Amazon EKS (Elastic Container Service for Kubernetes)

AWS Elastic Beanstalk

AWS Lambda

AWS Batch

AWS Lightsail

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%204.png)

Compute resources can be considered the brains and processing power required by applications and systems to carry out computational tasks via a series of instructions

Closely related to CPU and RAM on physical servers

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%205.png)

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%206.png)

### Amazon EC2 - Elastic Cloud Compute

<aside>
📌 **SUMMARY: Other fundamentals:** [https://cloudacademy.com/amazon-web-services/aws-storage-fundamentals-2016-course/](https://cloudacademy.com/amazon-web-services/aws-storage-fundamentals-2016-course/) - [https://cloudacademy.com/course/database-fundamentals-part-one-1064/course-introduction/](https://cloudacademy.com/course/database-fundamentals-part-one-1064/course-introduction/) - [https://cloudacademy.com/amazon-web-services/aws-networking-aws-160-course/](https://cloudacademy.com/amazon-web-services/aws-networking-aws-160-course/)

</aside>

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%207.png)

AMI’s are essentially templates for preconfigured EC2 instances which allow you to quickly launch a new EC2 instance based on the configuration within the AMI

It is possible to create your own AMI’s to help you speed up your own deployments

AMI’s are also available on the AWS Marketplace

Community AMI’s also exist which have been created by others and their configurations made available

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%208.png)

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%209.png)

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%2010.png)

Reserved instances are available on a 1 year or 3 year term

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%2011.png)

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%2012.png)

![Untitled](AWS%20Cloud%20%20e2c6a/Untitled%2013.png)

---

---