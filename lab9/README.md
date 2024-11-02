# GCP Infrastructure Configuration (PLEASE REFEER TO THE CSV FILE FOR ANY CLARIFICATON NEEDED)

This document details the configuration, purpose, and cost breakdown for various instances and services set up on Google Cloud Platform (GCP) for a scalable, secure, and efficient infrastructure.

---

## 1. Primary Compute Instances (n2-standard-2)

- **Machine Type**: n2-standard-2
- **vCPUs**: 2
- **RAM**: 8 GB
- **Region**: Taiwan (asia-east1)
- **Boot Disk**: SSD Persistent, 10 GiB
- **Instance Count**: 10
- **Operating System**: Debian, CentOS, CoreOS, Ubuntu, or BYOL

### Purpose and Rationale
These instances are likely configured for primary application workloads that require moderate compute and memory resources. With 2 vCPUs and 8 GB RAM per instance, they balance performance with cost efficiency, suited for medium-level application processing, web servers, or moderate backend services. The use of SSD persistent disks provides faster access speeds compared to HDDs, essential for applications with quick data retrieval needs. Hosting them in the asia-east1 (Taiwan) region may optimize latency and accessibility for users or operations located in that region.

### Why 10 Instances?
Having 10 instances allows for load distribution, redundancy, and scalability to handle peak traffic without compromising on performance. This setup also ensures high availability, as workloads can continue running even if some instances are temporarily unavailable.

### Monthly Cost Breakdown
- **Instance Cost**: $820.90 (for each instance)
- **Disk Cost**: $17.00 (for each instance)
- **Total for 10 Instances**: $837.90

---

## 2. Supporting Compute Instances (e2-micro)

### Configuration (mc1, mc2, mc3)

- **Machine Type**: e2-micro
- **vCPUs**: 0.25
- **RAM**: 1 GB
- **Regions**: Iowa (us-central1), Belgium (europe-west1), Taiwan (asia-east1)
- **Boot Disk**: Balanced Persistent Disk, 10 GiB
- **Instance Count**: 7 each in Iowa and Belgium, 6 in Taiwan
- **Operating System**: Debian, CentOS, CoreOS, Ubuntu, or BYOL

### Purpose and Rationale
e2-micro instances are lightweight and cost-effective, ideal for handling low-intensity tasks such as logging, health checks, or lightweight services that don’t require extensive resources. With only 0.25 vCPU and 1 GB RAM, they are particularly useful for background operations, service monitoring, or supporting functions that don’t demand intensive compute resources. The balanced persistent disks provide a middle ground between performance and cost, suitable for these auxiliary tasks. Deploying them across regions (Iowa, Belgium, Taiwan) ensures that any region-specific tasks can be executed locally, reducing latency for region-specific services.

### Why Different Counts (7, 7, 6 Instances)?
By adjusting the number of instances based on regional needs, the configuration allows for right-sizing the infrastructure based on specific workloads in each region. For example, regions with lower anticipated traffic may have fewer instances to keep costs minimal.

### Monthly Cost Breakdown
- **Iowa (mc1)**:
  - **Instance Cost**: $42.80
  - **Disk Cost**: $7.00
  - **Total for 7 Instances**: $49.80
- **Belgium (mc2)**:
  - **Instance Cost**: $47.09
  - **Disk Cost**: $7.00
  - **Total for 7 Instances**: $54.09
- **Taiwan (mc3)**:
  - **Instance Cost**: $42.48
  - **Disk Cost**: $6.00
  - **Total for 6 Instances**: $48.48
- **Total for all e2-micro Instances**: $152.37

---

## 3. High-Performance GPU Instance (a2-highgpu-1g)

- **Machine Type**: a2-highgpu-1g
- **vCPUs**: 12
- **RAM**: 85 GB
- **Region**: Iowa (us-central1)
- **Boot Disk**: Balanced Persistent Disk, 10 GiB
- **Instance Count**: 1
- **Operating System**: Debian, CentOS, CoreOS, Ubuntu, or BYOL
- **GPU**: Enabled

### Purpose and Rationale
This high-performance instance is essential for compute-intensive tasks like machine learning model training, data processing, or analytics workloads that require significant computational power. The a2-highgpu-1g instance provides a strong combination of 12 vCPUs and 85 GB of RAM, necessary for large datasets or high-throughput processing tasks. The GPU addition is particularly valuable for parallel processing tasks, image or video processing, or tasks requiring high computational power. Choosing us-central1 (Iowa) leverages lower costs associated with that region while still maintaining performance.

### Why Only 1 Instance?
Given the high cost of GPU instances, maintaining a single instance limits expenses while still fulfilling the needs of heavy processing tasks. Additionally, many GPU-intensive tasks can often be run asynchronously, allowing this single instance to serve multiple workloads over time.

### Monthly Cost Breakdown
- **Instance Cost**: $2,141.75
- **Disk Cost**: $1.00
- **Total**: $2,682.57

---

## 4. Secure Payment Processing Instances (c2d-standard-2)

### Configuration (pay1)

- **Machine Type**: c2d-standard-2
- **vCPUs**: 2
- **RAM**: 8 GB
- **Region**: Iowa (us-central1)
- **Boot Disk**: Balanced Persistent Disk, 10 GiB
- **Instance Count**: 1
- **Operating System**: Debian, CentOS, CoreOS, Ubuntu, or BYOL
- **Confidential VM**: Enabled

### Purpose and Rationale
The c2d-standard-2 instance is configured for secure, high-priority workloads related to payment processing, requiring both compute capability and enhanced security. Enabling Confidential VM ensures that data in use is encrypted, crucial for handling sensitive transactions and meeting compliance requirements for data protection. With 2 vCPUs and 8 GB RAM, this instance can process payment transactions smoothly while ensuring data security. The Iowa region allows for relatively lower costs without sacrificing access speed for North American operations.

### Why 1 Instance?
By designating a single instance with Confidential VM, security is prioritized without the need for multiple redundant instances, as payment processing typically requires robust but streamlined resources.

### Monthly Cost Breakdown
- **Instance Cost**: $66.28
- **Disk Cost**: $1.00
- **Total**: $79.57

---

## 5. Additional High-Security VM (c2d-standard-2)

### Configuration (Instance 4)

- **Machine Type**: c2d-standard-2
- **vCPUs**: 2
- **RAM**: 8 GB
- **Region**: Belgium (europe-west1)
- **Boot Disk**: Balanced Persistent Disk, 10 GiB
- **Instance Count**: 1
- **Operating System**: Debian, CentOS, CoreOS, Ubuntu, or BYOL
- **Confidential VM**: Enabled

### Purpose and Rationale
Similar to the payment processing instance in Iowa, this instance in Belgium (europe-west1) provides a secure, dedicated environment for sensitive workloads specific to European operations. Using Confidential VM technology offers an extra layer of security, ensuring data privacy and compliance with regional regulations. This setup helps meet GDPR requirements for data handling within the EU, making it suitable for operations with high-security needs.

### Why 1 Instance?
As with the Iowa payment processing instance, a single secure VM reduces costs while maintaining necessary security measures for sensitive data processing in the European region.

### Monthly Cost Breakdown
- **Instance Cost**: $72.98
- **Disk Cost**: $1.00
- **Total**: $86.27

---

## 6. Batch Processing Instance (e2-micro)

- **Machine Type**: e2-micro
- **vCPUs**: 0.25
- **RAM**: 1 GB
- **Region**: Iowa (us-central1)
- **Boot Disk**: Balanced Persistent Disk, 10 GiB
- **Instance Count**: 1
- **Operating System**: Debian, CentOS, CoreOS, Ubuntu, or BYOL

### Purpose and Rationale
The batch processing instance is configured with minimal resources, as it’s likely intended for low-priority, periodic tasks that don’t require real-time processing. With only 0.25 vCPU and 1 GB RAM, it efficiently handles background or asynchronous processes such as log processing, backups, or report generation. By using the Iowa region, it benefits from cost efficiency without impacting performance.

### Why 1 Instance?
A single instance suffices for batch tasks, given their asynchronous nature and low compute requirements, keeping costs low while performing necessary auxiliary functions.

### Monthly Cost Breakdown
- **Instance Cost**: $6.11
- **Disk Cost**: $1.00
- **Total**: $7.11

---

## 7. Data Analytics (BigQuery)

- **Configuration**: 100 baseline slots, 15 TiB storage, EU multi-region, Enterprise Edition
- **Monthly Cost**: $6,570.40

### Purpose and Use Cases
BigQuery enables large-scale data analytics with autoscaling, ideal for processing vast datasets. The EU storage meets GDPR compliance, while 200 autoscaling slots support peak demands.

---

## 8. Databases

### Cloud SQL (MySQL)
- **Configuration**: 16 vCPUs, 60.4 GB RAM, 5 TiB SSD, Iowa
- **Monthly Cost**: $1,661.43

### Purpose
Managed MySQL instance supports reliable transactional workloads with automated backups and scaling.

### Use Cases
Transaction processing, data analytics, user authentication.

### Bigtable
- **Configuration**: 4 nodes, 10 TiB SSD, Iowa
- **Monthly Cost**: $3,638.80

### Purpose
Bigtable is designed for high-throughput NoSQL applications, ideal for large datasets needing low-latency access.

### Use Cases
IoT data, recommendation engines, real-time analytics.

---

## 9. Networking (Cloud Load Balancing & CDN)

- **Configuration**: 100 GiB inbound/outbound data, CDN across North America and Europe
- **Monthly Cost**: $47.67

### Purpose
Load Balancing distributes traffic for high availability; CDN caches content to reduce latency.

### Use Cases
Web/mobile app performance, media delivery, global API distribution.

---

## 10. Storage (Cloud Storage)

- **Configuration**: 5,000 GiB in Iowa, Standard storage class
- **Monthly Cost**: $99.90

### Purpose
Object storage for files, backups, and static content. Ensures durability and high availability with regional replication.

### Use Cases
Backups, hosting static resources, analytics data.

---

## 11. Security (Cloud Key Management Service - KMS)

- **Configuration**: 4 key versions, 15,000 key operations
- **Monthly Cost**: $0.29

### Purpose
Centralized encryption management for securing sensitive data across GCP services.

### Use Cases
Data encryption, secure access control.
