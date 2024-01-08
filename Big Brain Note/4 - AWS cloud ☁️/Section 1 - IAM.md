# Region 
- clusters of Data centers
- How to choose Region?
  1. Compliance : Data governance and legal requirements
  2. Latency : close to your target audience 
  3. Available Service (Region Scoped)
    1. Amazon EC2 (IaaS)
    2. Elastic Beanstalk (PaaS)
    3. Lambda (FaaS)
    4. Rekognition (SaaS)
  4. Pricing
# AZ (Availability Zone)
# AWS Point of Presence (Edge Location)
IAM user VS root user
Each group has one policy which defines the permission 
```JSON
{
	"Version" : "version1",
	"Id": "tempId123",
	"Statement" : [
	{
		"Sid": "1",
		// statement id
		"Effect": "Allow", 
		// whether the statement allows or denies access (Allow / Deny)
		"Principal" : {
			"AWS" : ["root"]
		}, 
		// account/user/role to which this policy applied to
		"Action": "ec2:Describe*",
		// list of actions this policy allow or deny
		"Resource":"*",
		// list of resources to which the action applied to 
		"Condition" : "None"
		// conditions for when this policy is in effect
	},
	]
}
```

IAM role user can be assigned for specific services
IAM Access Advisor : show the services access granted to other users  

# IAM Summary
- Users: physical use, real people
- Groups: a lot of users
- Policies: define the allow or deny permissions
- Roles: For EC2 instances and services
- Audit: IAM credential report & IAM User Advisor

