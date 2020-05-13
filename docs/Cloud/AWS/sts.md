# STS (Security token service)
	- Management of temporary security credentials for both IAM or federated users
	- This service is used to give temporary credentials for AWS resources to trusted and authenticated entities. 
	- Since they are used dynamically and with a limited duration - these are some of the security advantages
	- Doesn’t not incur any costs
	- Doesn’t have user interface to manage STS
	- A token and the duration is assigned on the access request or API call
	- Token is passwordless
	- You cannot use AWS root user to assume role into different accounts. We have to use credentials of IAM user or an IAM role to call assume role.
	- Duration is can be limited from 15 to 1.5 day
	- Basically used when a person wants to access different accounts they can use STS  to temporarily assume a role in another account. 
	- Also a non-aws user can use identity federation to login to third party vendor, receive a token and wants access to an AWS environment.  
	- Good thing about STS is that it doesn’t involve passwords - 
	- Do STS Lab
	
	Use cases:
		- Identity federation and Web Identity Federation
		- Identity Federation - Active Directory/ADFS
		- Web Identity Federation - 

	Create a diagram
	Do a lab
