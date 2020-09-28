RDS:

1. Add a lifecycle hook to set an instance in a wait state, which prevents data loss

2. Cooldown period helps to ensure that your ASG doesn't launch/terminate instances before the previous scaling (we can also use CloudWatch alarm for triggering the scale down policy)

3. Termination policy is used to specify which instances to terminate first during scale

4. Use EBS General purpose SSD if you have small peaks with a low budget or use IOPS optimized

ASG:

1. Always check minimum instance count in other AZ's if question-related to AZ's down

S3:

1. Use S3 event notification with lambda for rare operations to make cost-effective

2. Check always question related to bucket level or object level (storage class and metadata)

3. You still get data sometimes after DELETE due to the eventual consistency property of S3

4. S3 provides read-after-write consistency for PUTS, you can download the file immediately

5. Use File Gateway to connect On-Premise application, you can connect Via API also

6. Use Pre-Signed always for giving access for a particular time even for internal users

7. S3 support at least 3,500 requests per second to add data and 5,500 requests per second for retrieval

8. Use Prefix for better performance

9. S3 supports 5GB direct PUT, use multipart upload supports 5TB

10. use server logging and clodTrail logging for S3 logs

11. Add configuration in S3 bucket CORS to allow PUT requests from web application URL

12. bucket URL (https://bucket-name.s3.Region.amazonaws.com/key name) or https://s3.Region.amazonaws.com/bucket-name

13. DELETE API call on the object does not delete the actual object but places a delete marker on the object. (it still in billing)

SQS:

1. Short poll runs even queue is in empty, use long poll it will reduce cost, default poll is short

2.

Amazon Aurora:

1. Aurora is fully manged with scalable and cost-effective

2. Replica lag (downtime while updating) is less than 100 milliseconds

VPC:

1. Use Bastion hosts for private instance SSH connection

2. We can't use VPC endpoint outside of VPC, Eg: use S3 Proxy for direct private connection from on-premise

3. You can create a flow log for a VPC, a subnet, or a network interface.

4. Border Gateway Protocol (BGP) Autonomous System Number (ASN). are required to create a virtual private gateway

5. egress-only Internet gateway is a VPC component that allows outbound communication over IPv6

6. Use ENI for fixed MAC address

Amazon/S3 Glacier:

1. It uses to store data in archive format, commonly used for in-frequent data

2. Vault is a group of archives, Vault Lock is a lock policy used to vaults

3. there are 3 types of retrievals (Expedited, Standard, Bulk), use Expedited for faster, use based on pricing

Cloud Formation:

1. Drift detection finds the changes/deletions in the template

IAM:

1. Use IAM roles for access AWS API for EC2 (use this for similar cases) 
