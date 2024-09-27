Lab 3 - Cloud Migration and Cloud Adoption – A Comparative Study of PaaS, IaaS, and SaaS Across Cloud Providers

The purpose of this lab is to provide me with a comprehensive understanding of cloud migration and cloud adoption strategies, focusing on the different service models offered by cloud providers: Platform as a Service (PaaS), Infrastructure as a Service (IaaS), and Software as a Service (SaaS).

![Capture](https://github.com/user-attachments/assets/329ec5fe-c295-4cad-9240-9ce98954ddaf)

Section 1: On-Premises Solution Design Description
Description of On-Premises Solution

1. Web Application (Monolithic)
Hosted on: Physical servers
Description: The web application is a monolithic application hosted on physical servers within the company's data center.

2. Backend Database
Hosted on: SQL server
Description: The backend database is an SQL server hosted on physical servers, responsible for storing and managing the company's data.

3. File Storage
Hosted on: Local file system
Description: File storage is managed using a local file system on physical servers, storing various files required by the web application and other services.

4. Networking
Handled by: Company-operated routers and firewalls
Description: Basic networking is managed by the company's own routers and firewalls, ensuring secure communication between different components.

5. Email Services
Description: Email services are used for client notifications, managed and operated within the company's infrastructure.

Explanation: The Web Application communicates with the Backend Database through the Network, allowing it to retrieve and store data efficiently. The Network also facilitates file storage by connecting to the File Storage component, ensuring that files can be stored and accessed seamlessly. Notifications and alerts are sent from the Network to clients via the Email Services, enhancing customer engagement and communication.

Section 2: Cloud Migration Design Description

![Capture2](https://github.com/user-attachments/assets/c7e0e695-9085-4f20-9174-8a3e5bfc08fa)
---

# Cloud Migration Design Description

## 1. Web Application Migration

**Current State:**  
The website is in a monolithic state, which is hosted on physical servers.

**Migration Strategy:**  
- **Initial Phase:** I would host the web application using a PaaS-based approach.
- **Reason:** The reason behind using PaaS is that it simplifies deployment and management and requires less support from developers compared to the IaaS approach.
- **Service Used:** I would host the web application on Heroku or maybe use Vercel.

---

## 2. SQL Server Migration

**Current State:**  
SQL Server is hosted on physical servers.

**Migration Strategy:**  
- **Initial Phase:** I would run my SQL Server on an Azure Virtual Machine, where I would utilize B1S and B1MS instances for performance. By pricing level, this is really the low-cost approach I am going with (IaaS).
- **Reason:** The reason behind using an IaaS-based approach is that data is one of the most crucial aspects when it comes to a company, so even if it costs a little extra, I will try to safeguard this as much as possible. Another reason is full control over everything; I can fine-tune the SQL Server based on my needs.
- **Service Used:** Azure Virtual Machine.

---

## 3. File Storage Migration

**Current State:**  
Regular file system.

**Migration Strategy:**  
- **Initial Phase:** I would host the file storage service application using a PaaS-based approach like S3 bucket.
- **Reason:** S3 is very easy to set up and use. It also provides scalable, durable, and secure storage with integrated data management features like lifecycle policies and access controls.
- **Service Used:** S3 Bucket, Azure Blob Storage.

---

## 4. Networking Migration

**Current State:**  
Company-operated routers and firewalls.

**Migration Strategy:**  
- **Initial Phase:** I would use cloud-native networking services like Azure Virtual Networks.
- **Reason:** Cloud-native networking services offer advanced networking features, including network segmentation, security groups, and VPN connectivity, which enhance security and scalability.
- **Service Used:** AWS VPC, Azure Virtual Network.

---

## 5. Email Services Migration

**Current State:**  
Email services for client notification.

**Migration Strategy:**  
- **Initial Phase:** I would use a SaaS-based approach here and would use Microsoft 365.
- **Reason:** SaaS email services provide reliable, scalable, and cost-effective solutions for sending emails without the need to manage the underlying infrastructure.

### Detailed Hybrid Migration Plan

1. **Assessment and Planning:**
   - Assess the current on-premises infrastructure.
   - Identify dependencies and potential challenges.
   - Create a detailed migration timeline.

2. **Web Application Migration:**
   - **Initial Phase (PaaS):** Host the web application on Heroku for both frontend and backend, or use Vercel for the frontend and Heroku for the backend.
   - **Future Phase (IaaS):** Rehost the web application to VMs in the cloud.
   - **Refactoring:** Gradually refactor the application to leverage cloud-native features and improve performance.

3. **Database Migration:**
   - **Initial Phase (IaaS):** Rehost the SQL server to a VM in the cloud.
   - **Future Phase (PaaS):** Migrate to a managed PaaS database service.
   - **Data Migration:** Use database migration tools to transfer data with minimal downtime.
   - **Testing:** Perform thorough testing to ensure data integrity and application compatibility.

4. **File Storage Migration:**
   - **Data Transfer:** Use cloud storage migration tools to transfer files to the cloud storage service.
   - **Integration:** Update the web application to interact with the new cloud storage service.

5. **Networking Migration:**
   - **Setup:** Configure cloud-native networking services to replicate the on-premises network setup.
   - **Security:** Implement security groups, firewalls, and VPN connections as needed.

6. **Email Services Migration:**
   - **Integration:** Update the web application to use the new SaaS email service.
   - **Testing:** Ensure that email notifications are sent correctly and reliably.

7. **Validation and Optimization:**
   - **Testing:** Perform end-to-end testing of the migrated components.
   - **Optimization:** Optimize the cloud resources for performance and cost-efficiency.
   - **Monitoring:** Set up monitoring and alerting to ensure the smooth operation of the migrated services.

8. **Go-Live:**
   - **Cutover:** Perform the final cutover to the cloud environment.
   - **Support:** Provide post-migration support to address any issues that arise.




