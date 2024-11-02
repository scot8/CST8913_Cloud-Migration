# Cost Analysis and Projections for GCP Infrastructure

This document provides a comprehensive three-year cost projection and optimization strategy for ShopPro International's cloud infrastructure on Google Cloud Platform (GCP). Each year's analysis includes a breakdown by service category, growth assumptions, and projected costs with strategic adjustments.

---

## Overview

This analysis covers:
- **Year 1 Baseline**: Current annual expenses.
- **Year 2 Projection**: Moderate growth and cost-saving measures.
- **Year 3 Projection**: High growth and long-term optimization strategies.

**Initial Yearly Cost (Year 1)**: $190,371.36  
**Projected Cost Growth (Year 2)**: $216,327.50  
**Projected Cost Growth (Year 3)**: $260,604.50  

---

## Year 1 - Baseline Costs

Based on current usage patterns, Year 1 serves as our baseline for analyzing costs. The breakdown below outlines the primary contributors:

| Service                    | Monthly Cost | Annual Cost   | Details                                                                                 |
|----------------------------|--------------|---------------|-----------------------------------------------------------------------------------------|
| **BigQuery**               | $6,570.40    | $78,844.80    | 100 slots, 15 TiB storage in EU, Enterprise edition                                     |
| **Bigtable**               | $3,638.80    | $43,665.60    | 4 nodes, 10 TiB storage in Iowa                                                         |
| **GPU (Compute Engine)**   | $2,682.57    | $32,190.84    | a2-highgpu-1g, 12 vCPUs, 85 GB RAM                                                      |
| **MySQL (Cloud SQL)**      | $1,661.43    | $19,937.16    | Custom instance, 16 vCPUs, 60.4 GB RAM, 5 TiB SSD in Iowa                               |
| **Cloud Monitoring**       | $993.30      | $11,919.60    | Real-time monitoring of infrastructure                                                  |
| **Compute Instances**      | $1,255.43    | $15,065.16    | Supporting VMs for various workloads                                                    |
| **Cloud Storage**          | $224.00      | $2,688.00     | General storage needs, including backups                                                |
| **Networking**             | $47.67       | $572.04       | Cloud CDN and Load Balancing                                                            |
| **Cloud Logging & KMS**    | $27.29       | $327.48       | Logging ($27) and Key Management Service ($0.29) per month                              |

Total **Year 1 Cost**: $190,371.36

---

## Year 2 - Moderate Growth with Strategic Adjustments

### Assumptions and Adjustments
- **Data Growth**: 20% annual increase in BigQuery, Bigtable, and Cloud Storage.
- **Compute Demand**: 15% increase to support new services.
- **Optimization Strategies**: Implement sustained and committed use discounts, lifecycle policies, and data partitioning.

### Adjusted Cost Breakdown

| Category                   | Projected Cost | Details                                                                                              |
|----------------------------|----------------|------------------------------------------------------------------------------------------------------|
| **Compute & GPU**          | $77,507        | 15% increase, 1-year committed use discounts (15-37% savings)                                        |
| **BigQuery**               | $72,463        | 20% growth offset by reserved slots and data partitioning                                            |
| **Bigtable & MySQL**       | $64,025        | Increased nodes and storage, with lifecycle policies and 3-year commitments                           |
| **Networking & CDN**       | $632           | Increased CDN usage with efficiency improvements                                                     |
| **Storage**                | $1,197         | 20% growth, lifecycle policies to archive older data                                                 |
| **Cloud Monitoring & Security** | $1,023  | Consolidated KMS key usage for reduced operation costs                                               |

**Total Year 2 Cost**: $216,327.50

---

## Year 3 - High Growth with Long-Term Optimizations

### Assumptions and Adjustments
- **Data Growth**: Continued growth across all data services.
- **Compute Demand**: Additional 20% growth to support new workloads.
- **Optimization Strategies**: Transition to 3-year commitments, Coldline storage, and data lifecycle management.

### Adjusted Cost Breakdown

| Category                   | Projected Cost | Details                                                                                              |
|----------------------------|----------------|------------------------------------------------------------------------------------------------------|
| **Compute & GPU**          | $94,500        | 20% growth, 3-year committed use discounts reducing costs by up to 57%                               |
| **BigQuery**               | $87,000        | Increased storage and slots with further partitioning and clustering                                 |
| **Bigtable & MySQL**       | $77,000        | Additional storage and nodes, Coldline storage for older data                                        |
| **Networking & CDN**       | $750           | Geographic load balancing to reduce regional network traffic                                         |
| **Storage**                | $1,350         | 30% growth, aggressively archiving older data                                                        |
| **Cloud Monitoring & Security** | $1,250   | Optimized KMS access patterns                                                                        |

**Total Year 3 Cost**: $260,604.50

---

## Three-Year Cost Projection Summary

| Category                  | Year 1 Baseline | Year 2 Projection | Year 3 Projection |
|---------------------------|-----------------|--------------------|--------------------|
| **Compute & GPU**         | $46,140         | $77,507           | $94,500           |
| **BigQuery**              | $78,844.80      | $72,463           | $87,000           |
| **Bigtable & MySQL**      | $63,602.76      | $64,025           | $77,000           |
| **Networking & CDN**      | $572.04         | $632              | $750              |
| **Storage**               | $2,688          | $1,197            | $1,350            |
| **Monitoring & Security** | $12,247.08      | $1,023            | $1,250            |

**Total Cost by Year**  
- **Year 1**: $190,371.36  
- **Year 2**: $216,327.50  
- **Year 3**: $260,604.50  

---
