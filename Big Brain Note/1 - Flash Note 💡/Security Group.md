- Stateful, virtual firewalls that control inbound and outbound traffic for Amazon EC2 instances. They are associated with individual EC2 instances, not subnets. 💡[[NACL(Network Access Control List)|NACL]] associate with the subnets.
- all inbound traffic is blocked by default
- all outbound traffic is allowed by default
- STATEFUL (if you allow inbound traffic from a specific IP, the corresponding outbound response traffic is automatically allowed.)
- [[EC2]] Instances can belong to multiple security groups.
- To block specific IP address: NOT Security Group; you need [[NACL(Network Access Control List)|NACL]] to achieve this 
- can have up to 10000 SG per Region
- each SG has 60 inbound rules and 60 outbound rules
- can have 16 SG associated to an [[Elastic Network Interface]]
- Security Groups are stateless at the group level but stateful at the rule level.

# [[NACL(Network Access Control List)|NACL]] VS SG

| item          | NACL                                                                   | SG                                |
| ------------- | ---------------------------------------------------------------------- | --------------------------------- |
| Association   | subnets                                                                | EC2 instances                     |
| Statefulness  | Stateless require both inbound and outbound rules for expected traffic | Stateful allow traffic by default |
| Granularity   | less                                                                   | more                              |
| Default Rules | allow all                                                              | deny all inbound                  |
| Use case      | For controlling traffic between subnets                                | for securing instances                                  |
