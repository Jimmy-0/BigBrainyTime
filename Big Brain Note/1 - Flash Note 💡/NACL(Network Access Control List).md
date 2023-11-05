
- NACLs are stateless(i.e. any allowed inbound is also allowed outbound), virtual firewalls that control inbound and outbound traffic for Amazon VPC subnets.
- They act as an additional layer of security for your VPC, complementing security groups.
- Each subnet can have 1 NACL at a time
- NACLs don't support logging directly. Consider using [[VPC#VPC Flow Logs|VPC Flow Logs]] for visibility into network traffic.
⛔️ **Limitations:**
   - NACLs cannot be directly associated with instances; they are associated with subnets.
   - They are not as granular as security groups, which operate at the instance level.


**Exam Tips:**

- Understand the concept of NACLs as stateless network security controls.
- Know the default NACL and its permissiveness.
- Be able to create and modify custom NACLs and their rules.
- Differentiate NACLs from security groups and when to use each.
