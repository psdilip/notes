# AWS WAF

Protects your AWS resources from web exploits and DDOS attacks

WAF blocks traffic based on conditions
	- ALB
	- API Gateway
	- CloudFront

When using WAF on ALB, rules run on region

Conditions - define basic characteristic that would analyze within a web request
Rules - we can combine multiple conditions into rules to precisely target requests
	- Two types of rules: Regular Rule & Rate-Based rule
	- Regular Rule 
	1. If request comes from a certain IP address
	2. they include to be SQL-like code
	- Rate-Based rule = Regular Rule + Rate limiting feature
	1. If request comes from a certain IP address
	2. they include to be SQL-like code
	3. If requests exceeds 1000 request in 10 minutes
		
Web ACL 
Defines action taken against a rule
If a rule is set, what “Action” should we take now?
- Types of action: Allow, Block, Count

Associate in WAF
	- Association defines to which entity WAF is associated to
	- WAF cannot be associated with EC2 instances directly
	- Supported Association: ALB and Cloudfront

To block particular traffic
1. Head to AWS WAF service
2. Create a web access control list
    1. Create a web acc name
    2. Resource type to associate with the ACL (typically a Application load balancer or Cloudfront distributions)
    3. Choose the exact AWS Resource to associate it with
3. Create conditions (filters) that you want to use to allow or block incoming requests that are forwarded to your AWS Resources
    1. Examples of conditions
        1. Cross-site scripting match conditions
        2. Geo match conditions
            1. Lets you allow, block or count web requests based on geographic origin
        3. IP match conditions
            1. Lets you specify the IP address range that you want to use to control access to your content
        4. Size constraint conditions
            1. Checks for the user requests that have sizes too large or too small
        5. SQL Injection match conditions
            1. Lets you inspect for SQL queries within the web request
        6. String and regex match conditions
            1. Specific string match conditions that you to use on the web request to control access to your content
    2. Create any Conditions
        1. Type in your condition information
    3. Create rule
        1. Specify the conditions that you want to use to filter web requests
        2. Choose action of allow or block
    4. Review and create
