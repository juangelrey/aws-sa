# Storage Portfolio

![alt text](images/storage_portfolio.png)


## EBS

### Features
- Single AZ. Next to EC2
- same as direct attached volumes
- HDD or SSD
- pay for the provisioned size, type, and provisioned performance
- integrated snapshots
### Use Cases


## EFS

### Features
- Regional service & multiple AZ
- pay only for the storage that you consume.
- Integrates with AWS DataSync and AWS Transfer Family for transfer workloads
- Integrates with Amazon EC2, AWS Lambda, Amazon Elastic Container Service (Amazon ECS), and Amazon Elastic Kubernetes Service (Amazon EKS) for compute processing

### Use Cases


## FSx for Windows File Server

### Features
- SMB protocol
- You pay for the capacity that you provision.
- Integrates with AWS DataSync for transfer workloads.

### Use Cases


## FSx for Lustre

### Features
- for high-performance computing environments
- pay for the provisioned capacity and the provisioned performance characteristics.
- Integrates with Amazon EC2, AWS Lambda, Amazon Elastic Container Service (Amazon ECS), and Amazon Elastic Kubernetes Service (Amazon EKS) for compute processing


### Use Cases



## S3

### Features
- across multiple Availability Zones by default
- pay for the capacity you use plus access charges.
- Cross-Region Replication for increased availability.
- S3 buckets are globally unique 
- S3 supports individual file sizes up to 5 TB.


### Use Cases



## Hybrid

### Types
- AWS Outposts: brings AWS services into your local data center
    - Natively supports Amazon EBS volumes. 
    - Connectivity to the AWS required for the service link.
    - AWS owned and managed equipment. 
- AWS Storage Gateway: Gateways provide a replication service between the on-premises system
    - Amazon S3 File Gateway: files as objects in Amazon S3 in AWS. You can use NFS or SMB file access protocols.
    - Amazon FSx File Gateway: using the open standard SMB protocol.
    - Tape Gateway
        - Data is stored in an AWS managed Amazon S3 bucket
    - Volume Gateway
        - Snapshots are stored in AWS as Amazon EBS snapshots.


### Use Cases



## Snow

### Types
- AWS Snowcone: for smaller data transfer jobs
- AWS Snowball Edge: for transfer jobs between ~30 terabytes and 1 petabyte
    - Snowball Edge Storage Optimized without compute option provides a cost optimized solution for larger data transfer jobs that do not require compute processing.
- AWS Snowmobile: from several petabytes to exabytes in scale


### Use Cases


## CloudEndure 

### Features
- limited number of AWS Regions.
- after application is staged, you can change over to full use with higher-performing resources in AWS. 


### Use Cases



# Making decision

1. Is it new or existing workflow? New workflows often require experimentation and discovery, modular design approach 
2. Known workflow requirements? interoperability, expand, recommended configuration, estimated future, existing bottlenecks
3. What is the type of use case? high performance computing option, replatforming, forming a data lake, creating DR, solving retention
4. What are the requirements for storage location?  if workflow remote, latency, store in AWS or premises
5. What are the requirements for storage type? supported storage, multiple types, if object storage (cost savings),  reliability and durability requirements
6. What are the requirements for storage performance?  IOPS or throughput intensive, avg/min/max IOPS, latency sensitive, 
7. What are the requirements for access protocol? file access protocol supported, Linux vs Windows,
8. What are the requirements for data transfer? connectivity constraints, SFTP/FTPS/FTP, sync or scheduled, Cross-region, on premises and/or in cloud
9. What are the requirements for data protection? regular backups, retention, compliance, snapshots, long term archival
10. What is the best combination of storage services? 