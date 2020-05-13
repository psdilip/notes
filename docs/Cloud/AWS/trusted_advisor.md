# AWS Trusted Advisor

https://n2ws.com/blog/aws-automation/aws-trusted-advisor

This AWS Resource inspects your resources and gives real time recommendations based on Cloud best practices. Its primary purpose include 
- Cut down costs
- Follow cloud best practices
- helps customers increase performance
- Improve security 

Customers will get checked based on the following:
	- Cost optimization: Highlights unused resources
		- Example: If loadbalancers are idle are not attached to anything
	- Performance - recommendations that help with speed and responsiveness to your applications
		- helps you avoid resource starvation for EC2, EBS, VPC and ELB
		- Example: Checks your EC2 Cpu utilization, if its above a certain x% for x days it will send alerts
	- Security - identifies security settings
		Checks for the following:
			- Security Groups
			- IAM Use
			- MFA on Root Access
			- EBS Public Snapshots
			- RDS Public snapshots
		- Example: Checks if you have MFA installed in your root accounts
	- Fault Tolerance - looks at your redundancy shortfalls, over utilized resources
		- Example: If you have Amazon RDS Multi-AZ, it will check if you have a single availability zone 
	- Service Limits - 

Note**
- You have to refresh every 5 minutes for updated checks

Not all checks are available to all customers

Business and Enterprise Support Customers has access to
- Full set of checks
- Notifications
    - Weekly updates
    - Create alerts and automate actions with Cloudwatch
- Programmatic access
    - Retrieve results from the AWS Support API

Checks available to all customers
- 