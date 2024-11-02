# GCP Infrastructure Configuration

This document details the configuration and purpose of various instances and services set up on Google Cloud Platform (GCP) for a scalable, secure, and efficient infrastructure.

---

## 1. Primary Compute Instances (n2-standard-2)

- **Machine Type**: `n2-standard-2`
- **vCPUs**: 2
- **RAM**: 8 GB
- **Region**: Taiwan (`asia-east1`)
- **Boot Disk**: SSD Persistent, 10 GiB
- **Instance Count**: 10
- **Operating System**: Debian, CentOS, CoreOS, Ubuntu, or BYOL

### Purpose and Rationale
Primary instances configured for moderate application workloads like web servers or backend services, balancing performance with cost efficiency. SSD persistent disks provide fast access speeds essential for quick data retrieval.

### Why 10 Instances?
Supports load distribution, redundancy, and scalability for peak traffic and high availability.

### Monthly Cost Breakdown
- **Instance Cost**: $820.90 (each instance)
- **Disk Cost**: $17.00 (each instance)
- **Total Cost**: $837.90 for 10 instances

---

## 2. Supporting Compute Instances (e2-micro)

- **Machine Type**: `e2-micro`
- **vCPUs**: 0.25
- **RAM**: 1 GB
- **Regions**: Iowa (`us-central1`), Belgium (`europe-west1`), Taiwan (`asia-east1`)
- **Boot Disk**: Balanced Persistent Disk, 10 GiB
- **Instance Count**: 7 in Iowa and Belgium, 6 in Taiwan
- **Operating System**: Debian, CentOS, CoreOS, Ubuntu, or BYOL

### Purpose and Rationale
Used for low-intensity tasks such as logging, health checks, and monitoring, balancing performance and cost with `e2-micro` instances.

### Monthly Cost Breakdown
- **Iowa**: $49.80
- **Belgium**: $54.09
- **Taiwan**: $48.48
- **Total Cost**: $152.37 for all e2-micro instances

---

## 3. High-Performance GPU Instance (a2-highgpu-1g)

- **Machine Type**: `a2-highgpu-1g`
- **vCPUs**: 12
- **RAM**: 85 GB
- **Region**: Iowa (`us-central1`)
- **Boot Disk**: Balanced Persistent Disk, 10 GiB
- **Instance Count**: 1
- **GPU**: Enabled

### Purpose and Rationale
Handles compute-intensive tasks like machine learning model training and data processing, utilizing high vCPU, RAM, and GPU power for parallel processing.

### Monthly Cost Breakdown
- **Instance Cost**: $2,141.75
- **Disk Cost**: $1.00
- **Total Cost**: $2,682.57

---

## 4. Secure Payment Processing Instance (c2d-standard-2)

- **Machine Type**: `c2d-standard-2`
- **vCPUs**: 2
- **RAM**: 8 GB
- **Region**: Iowa (`us-central1`)
- **Boot Disk**: Balanced Persistent Disk, 10 GiB
- **Instance Count**: 1
- **Confidential VM**: Enabled

### Purpose and Rationale
Configured for secure payment processing, with Confidential VM enabled for encrypted data in use, critical for compliance and security in financial transactions.

### Monthly Cost Breakdown
- **Instance Cost**: $66.28
- **Disk Cost**: $1.00
- **Total Cost**: $79.57

---

## 5. Additional High-Security VM (c2d-standard-2)

- **Machine Type**: `c2d-standard-2`
- **vCPUs**: 2
- **RAM**: 8 GB
- **Region**: Belgium (`europe-west1`)
- **Boot Disk**: Balanced Persistent Disk, 10 GiB
- **Instance Count**: 1
- **Confidential VM**: Enabled

### Purpose and Rationale
High-security instance for sensitive data handling in Europe, ensuring GDPR compliance through Confidential VM.

### Monthly Cost Breakdown
- **Instance Cost**: $72.98
- **Disk Cost**: $1.00
- **Total Cost**: $86.27

---

## 6. Batch Processing Instance (e2-micro)

- **Machine Type**: `e2-micro`
- **vCPUs**: 0.25
- **RAM**: 1 GB
- **Region**: Iowa (`us-central1`)
- **Boot Disk**: Balanced Persistent Disk, 10 GiB
- **Instance Count**: 1

### Purpose and Rationale
For low-priority, asynchronous tasks such as logging and backups.

### Monthly Cost Breakdown
- **Instance Cost**: $6.11
- **Disk Cost**: $1.00
- **Total Cost**: $7.11

---

## 7. Data Analytics (BigQuery)

- **Configuration**: 100 baseline slots, 15 TiB storage, EU multi-region, Enterprise Edition
- **Monthly Cost**: $6,570.40

### Purpose and Use Cases
Supports large-scale data analytics, data warehousing, and real-time analytics, meeting GDPR compliance through EU multi-region storage.

---

## 8. Databases

### Cloud SQL (MySQL)
- **Configuration**: 16 vCPUs, 60.4 GB RAM, 5 TiB SSD, Iowa
- **Monthly Cost**: $1,661.43

Supports transactional workloads, data analytics, and user authentication with managed backups and scaling.

### Bigtable
- **Configuration**: 4 nodes, 10 TiB SSD, Iowa
- **Monthly Cost**: $3,638.80

Designed for high-throughput NoSQL applications, including IoT data, recommendation engines, and real-time analytics.

---

## 9. Networking (Cloud Load Balancing & CDN)

- **Configuration**: 100 GiB inbound/outbound data, CDN across North America and Europe
- **Monthly Cost**: $47.67

### Purpose and Use Cases
Distributes traffic for high availability, with CDN to reduce latency in global applications.

---

## 10. Storage (Cloud Storage)

- **Configuration**: 5,000 GiB in Iowa, Standard storage class
- **Monthly Cost**: $99.90

Used for object storage, backups, static content, and analytics data with regional replication.

---

## 11. Security (Cloud Key Management Service - KMS)

- **Configuration**: 4 key versions, 15,000 key operations
- **Monthly Cost**: $0.29

### Purpose and Use Cases
Centralized encryption management across GCP services, supporting data encryption and secure access control.

---

This infrastructure setup is designed to support a scalable, secure, and efficient environment, meeting specific application, security, and compliance needs while balancing cost-effectiveness.
