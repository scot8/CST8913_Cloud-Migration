# Purpose of lab 4
Design Rehosting Migration V2 in your Cloud Migration course is to develop a high-level design (HLD) document for a lift-and-shift migration of an application consisting of two virtual machines: WebServerVM and SQLVM

![Untitled diagram-2024-10-06-180554](https://github.com/user-attachments/assets/df380630-de6b-4544-9e7e-f0d0e2a2fe60)

## Components

1. **WebServerVM**:
   - **Node.JS**: This represents the existing virtual machine (VM) hosting a Node.js application.

2. **SQLVM**:
   - **SQL Server Database**: This represents the existing VM hosting a SQL Server database.

3. **Docker Image**:
   - The Node.js application from WebServerVM is containerized into a Docker image.

4. **Azure Container Registry (ACR)**:
   - The Docker image is pushed to ACR, a managed Docker registry service in Azure.

5. **Azure Kubernetes Service (AKS)**:
   - **Node.js Application**: The containerized Node.js application is deployed to AKS.
   - **Kubernetes Pods**: The application runs within Kubernetes pods, which are the smallest deployable units in Kubernetes.
   - **Traffic Distribution**: AKS uses a load balancer to distribute incoming traffic across multiple instances of the application for high availability and scalability.

6. **Azure Managed SQL Database**:
   - The SQL Server database from SQLVM is backed up and migrated to Azure SQL Database, a fully managed relational database service.

## Interactions

1. **Containerization**:
   - The Node.js application on WebServerVM is containerized into a Docker image.

2. **Pushing to ACR**:
   - The Docker image is pushed to Azure Container Registry for storage and management.

3. **Deployment to AKS**:
   - The Docker image is deployed from ACR to the AKS cluster.

4. **Running in Kubernetes Pods**:
   - The Node.js application runs within Kubernetes pods in the AKS cluster.

5. **Traffic Distribution**:
   - A load balancer in AKS distributes incoming traffic across multiple pods to ensure high availability and scalability.

6. **Database Migration**:
   - The SQL Server database on SQLVM is backed up and migrated to Azure Managed SQL Database.
