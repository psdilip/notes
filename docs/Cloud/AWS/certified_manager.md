# AWS Certificate Manager
	- Manages SSL certifications for your web applications
		- SSL stands for secure socks layer. Its a security protocol that is used to secure data between two machines using encryption
		- Without SSL, hacker can spy and steal user personal information like credit card and username/password
		- How does it work?
			- SSL certificates uses public key cryptography which involves two keys which are long strings of randomly generated numbers
			- Two keys are public and private key.
			- A public key is known to the server and available via public domain. It is used to encrypt message.
			- If Alice is sending a message to Bob. She will encrypt with bob’s public key.
			- If bob wants to decrypt it, he can only do it by using his private key. Only bob has this private key
			- If a hacker gets Alice’s message before Bob does, all the see is cryptographic code that they cannot break 
		- Example:
			- When you own a company, you would your customers to feel safe when they visit your website
			- So you would need to apply for SSL certificate from a Certificate Authority
			- There different types of SSL you can choose from
			- Your certificate authority will then verify its you as the business owner and your website and business is real 
			- Once verified you will get the SSL certificate, you can then install on your web server
			- When your server connects with your customers web browser an SSL handshake is performed
			- This SSL Handshake makes sure the certificate is valid
			- Now when your customer makes an order, their private information is secured with an ssl certificate. They are sure its a safe and legitimate website
			- TODO: How SSL handshake works
			- When a certificate is successfully installed on your server, the application protocol HTTP will change to HTTPS
	- Benefits
		- Keeps data secure between servers
		- Builds/Enhances customer trust
 

	- Region based - can be applied to resources in that region
	- Native integration
		- ELB
		- Cloudfront
		- Elastic Beanstalk
		- API Gateway
		- Route 53 - to perform DNS checks as part of the certificate-missing process
	- No cost with certificates, only the underlying resources that are used are billed
	- Certificates automatically renew when actively used with support services
	- Removes the manual process burden of buying, uploading, and renewing
	- 


Description
Use cases
Examples 
Tutorial
Cost
Pros