# What is S3

- Amazon S3 is one the main building blocks of AWS
- It is 'infinitely Scaling' storage
- Many websites/businesses use S3 as a backbone of their operation
- Most AWS Services use S3 for integration

## use cases

- Backup and storage
- Disaster recovery
- Archive storage
- Application hosting
- Media hosting
- Data analytics
- Software delivery
- Static website hosting 

## Buckets

- S3 uses 'Buckets' (directory) to store 'objects' (files)
- Buckets must have a globally unique name (accross all regions)
- Buckets are defined within a region
- Naming convention
   - No uppercase letters 
   - No underscores
   - 3-63 characters long
   - Not an IP
   - Must Not start with special character
   - Must not start with prefix xn--
   - Must not end with suffix -s3alias

## Objects

- Objects in S3 have a 'Key'
- A Key is the full path to the object + object name
  - eg. s3://folder/folder/My-object.txt
- Objects are not placed in 'directories' so the key is essentially just a very long name.
- Max object size is 5TB(5000GB)
  - If uploading more than 5GB, upload must be done in stages "Multi-Part upload"

## Creating a Bucket

## versioning

## Replication

CRR - Cross Region Replication
SRR - Same Region Replication

- versioning must be enabled in source and target bucket for replication to work
- A New IAM Role must be created

## Static website hosting

## Storage Classes


  - Object -> properties -> 'Edit' Storage Class
  - Select New Storage Class

## lifecycle rules

- Bucket -> Management -> Lifecycle Rules
- Add new rule to automate archiving tiers of files
- Select 'Rule Actions'
- Set transitions - by default the next available tier will be selected


## S3 Encryption

- Server Side Encryption - Default action, objects will be encrypted automatically by AWS to provide server side encryption
- Client Side Encryption - The user encrypts the files/data before uploading to AWS S3 Storage

## IAM Access Analyzer for S3

- Ensures that only intended people can access the S3 Bucket
- Analyses Policies, S3 ACLs and S3 Access Point Policies
- Review access analyzer to see which buckets are public and shared with other accounts/

## AWS Snow Family

- Highly secure, portable devices to collect data at the edge and migrate data in/out of AWS. It is a physical device sent to the customer, data is loaded locally and shipped back to AWS.

- Data Migration - Snowcone, Snowball Edge, Snowmobile!
  
![Data Migration](<Screenshots/Screenshot 2024-01-24 145931.png>)


  - Snowball Edge 
     - Large Device sent to the customer
    - Can hold TBs or PBs of data
    - Pay per data transfer job
    - Provides block storage and S3 object storage
    - Storage Optimized - 80TB of HDD capacity
    - Compute Optimizerd - 42TB of HDD or 28TB of NVMe capacity
  - Use Cases 
    - Large Data Cloud Migrations
    - Data Centre Decommission
    - Disaster Recovery 

  - Snowcone/Snowcone SSD
    - Small, rugged portable device that can withstand harsh environments
    - Used for computing, storage and data transfer
    - Snowcone - 8TB of HDD Capacity
    - Snowcone SSD - 14TB of SSD Capacity
    - Must provide own batteries and cables
    - Used where Snowball devices do not fit
    - Can be sent back to AWS offline or connected to the internet to use AWS DataSync to transfer data. 
  
  -  AWS Snowmobile
     -  This is a Physical Truck!
     -  Can transfer exabytes of data(1EB = 1,000PBs = 1,000,000TBs)
     -  Each Snowmobile has 100PB
     -  Can use multiple in parallel extremely large transfers
     - High Security - Temperature Controlled, GPS, 24/7 CCTV. 



- Edge Computing - Snowcone, Edge
 - Process Data while it is being created on an EDGE LOCATION(Limited/no internet connection) 
 - Use a Snowball or Snowcone device to do edge computing
 - Can be shipped back to AWS for Data processing





