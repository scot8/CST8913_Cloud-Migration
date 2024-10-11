# Purpose of lab 4
The purpose of this lab is to design a High-Level Design (HLD) document for migrating a 3-tier eCommerce application to a cloud-native architecture, focusing on scalability, availability, and disaster recovery. Students will learn to create a solution diagram and outline the migration process while leveraging cloud services from providers like AWS or GCP

![png](https://github.com/user-attachments/assets/b6646e4b-4ec8-4ab0-816c-a0e4abbe6014)

## Application Overview

The current eCommerce application is structured in a 3-tier architecture consisting of:

Frontend Web Server - Currently hosted on a WebAppVM.
Backend API Server - Running on an APIVM.
SQL Database - Managed on a DBVM.
The migration to a cloud-native architecture on AWS aims to enhance scalability, availability, and disaster recovery while ensuring minimal downtime during the transition.

## 2. Target Architecture Description

**Load Balancer**: For the frontend and backend, I used AWS Elastic Load Balancer to distribute traffic across multiple instances of the frontend web server. 

**Auto Scaling**: Additionally, I implemented an Auto Scaling Group for both the frontend and backend, which adjusts the number of instances based on demand, allowing the system to handle varying loads by automatically scaling instances.

**RDS**: For the SQL database, I utilized Amazon RDS (Relational Database Service) to manage the relational database, which includes features like automatic backups, patch management, and high availability. Amazon RDS allows for scaling of any relational database and provides backup options to restore to a specific point in time. Since its pricing model is pay-as-you-go, I can easily scale down based on my needs.

**User:** The end user who uses the application.

**Amazon Route 53:** Translates the user's DNS request into the appropriate IP addresses for the load balancers, directing traffic to the AWS infrastructure.

**EC2:** Deployed both the frontend and backend on separate EC2 instances.


## Scalability, Availability, and Disaster Recovery

- **Scalability**: The architecture employs auto-scaling groups for both frontend and backend services, allowing the application to handle fluctuating traffic efficiently. The Amazon RDS Read Replica ensures that read requests are offloaded from the primary database, improving performance during high traffic periods.

- **Availability**: The use of Elastic Load Balancers ensures that the application remains available even if one or more EC2 instances fail. AWS provides a highly available infrastructure with multi-availability zones to further enhance uptime.

- **Disaster Recovery**: Regular automated backups of the RDS database, coupled with read replicas, ensure data durability. In case of a failure, the system can be quickly restored within the required downtime of less than 2 hours.

### Migration Process

1. **Setting up the cloud**:
   - I will configure VPC, Subnets all the networking parts.
   - Setup AWS ec2 instances, Elastic Load balancer for the frontend and backend.
   - Configure Auto Scaling Groups for the API server.
   - Set up RDS for keep it ready for data migration.

2. **Data Migration**:
   - I will use a AWS Database Migration Service (DMS) to migrate data from the on-premises SQL Database to Amazon RDS.

3. **Application Deployment**:
   - I will deploy the frontend and backend applications on EC2 instances within the respective auto-scaling groups.
   - Configure Elastic Load Balancers to route traffic to the newly deployed instances.

4. **Testing**:
   - User acceptance testing to ensure the application meets performance expectations.

5. **Rollback Strategy**:
   - Ensure backups are available to restore the database to its previous state if necessary.
   - Create a rollback plan.


