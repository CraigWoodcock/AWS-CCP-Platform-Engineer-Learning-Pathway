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

