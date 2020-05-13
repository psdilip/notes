# IAM
Root Account
	- Best practices
		- Keep this account to a minimal use like to add new accounts, delegate access, view billing (extra).
		- Dont enable programmatic level access on the root account as it contains unrestricted access to your resources
		- Enable MFA on the root user

IAM User
	- Can be part of multiple groups
	- When user gets created, he/she will have implicit deny access to all the resources
	- Credentials should never be shared with others

IAM Roles
	- “Roles are a secure way to grant trusted entities access to your AWS Resources”
	- Entities (AWS resources, user outside of the account) can assume this role
	- Roles with AWS Services
		- Cannot assign policies to AWS services, should use IAM Roles
	- Each resource can use one role at a time
	- Attach roles to give permissions from resource to resource
	- For example: 
		- Ec2 needs access to create an SNS topic
		- Lambda needs to have access to store Cloud watch logs
	- Other users
		- Cross account delegation
		- Identity Federation
			- Users outside of AWS can assume a particular role to gain access to resources
IAM Groups
	- Best practice is to apply policies at the group level
	- We can’t nest groups within groups
	- Create groups based on function (ex. Database admins, Developers, Testers)

IAM Policies
	- JSON formatted permission documents 
	- Assign least privilege permissions
	- Managed Policies
		- A standalone policy that is managed by AWS
		- Reusable
	- Benefits
		- Automatically updated when a new api gets released
	- Customer Policies
		- Policies that we create on our own
		- Reusable
	- Benefits
		- You can modify based on your environment
	- Inline Policies
		- You can assign a policy to an IAM entity (Role, User, Group) and its only restricted for that entity
		- Not reusable
	- Policy parameters
		- Effect - can be either allow or deny
		- Action - set of AWS resource permissions to allow or deny
		- Resource - defined in ARN, an AWS resource 
		- Principal -
		- Sid - Optional. Use it as a description of the policy
		- Condition - 
MFA 	- Enable MFA for users
	- Time based codes, acts as an double authentication when logging into AWS Accounts
	- Example Apps: Google Authenticator, Authy Authenticator
	- Security best practice
	- More layers of authentication to your system the better
	- With logins, MFA can also be used when deleting objects to make sure they are authorization, and prevents accidental deletion. 

Notes- 
- When a new s3 api is available, AWS automatically enables them in their AWS Managed policies and customers would need to update all their inline/customer managed policies to the new api call if needed
	- Implicit Deny (Default) - AWS’s Philosophy is the Deny everything by default. Deny is “implied”
	- Explicit Allow - Overrides Implicit Deny, basically allows initial permissions. 
	- Explicit Deny - Overrides the explicit allow, this cannot be overridden.

	By default
		- All requests are denied (Implicit Denied)
		- Explicit allow overrides the default
		- Explicit deny overrides any defaults