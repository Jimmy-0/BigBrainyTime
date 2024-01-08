Elastic compute cloud / IaaS 
## Naming convention
`m5.2xlarge`
- m : instance class
- 5 : generation
- 2xlarge: size within the instance class
  
  ### Compute Optimized
- Btch processing workload
- Media transcoding
- HPC
- ML
- Gaming
### Memory Optimized
- High performance, SQL/non-SQL database
- distributed web cache
- In-memory database storage
- real-time processing of unstructured data 
### Storage Optimized
- High frequency online transaction processing system
- Cache of in-memory database 
- Data warehousing application
- Distributed file storage
### Security Groups
- Can be one to many 
- like the firewall 
- control the traffic in and out to the EC2 Instances 
- only contain allow rules
- rules can be referenced by IP or security group
- inbound traffic is blocked by default
- outbound traffic is allowed by default
- can be attached to multiple instances 
## Classic Port
`22` : SSH
`21` : FTP - upload into file share 
`22` : SFTP - upload files using SSH
`80` : HTTP - unsecured web
`443` : HTTPS - secured web
`3389` : RDP (Remote  Desktop Protocol)


## EC2 Hibernate
- available for On-demand, reserved and spot instances 
- 