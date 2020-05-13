# KMS (Key management Service)
- Easy way to control access to your data using encrypted keys
- This service is integrated with EBS, S3, Redshift
- Region specific so you can’t access keys from other regions
- If data is encrypted with a key, you won’t be able to retrieve the data if the key is lost
- You can audit KMS key usage via CloudTrail, (need to grant the compliance officer with respective permissions)
- You can access KMS through IAM encryption keys or the AWS KMS itself
- You can use default KMS keys if you choose not to use custom keys. Their Alias is formatted like this “aws/servicename”

How to create a KMS Key
	- Open the service
	- Create an alias
	- Add tags (optional)
	- Choose your key administrators
		- They have permissions to edit, enable, disable and rotate keys
	- Key usage permissions
		- Choose the users that can use the Custom Managed Key to encrypt or decrypt data with AWS KMS API
		- You can also add other AWS accounts to use this key
	- Review key policy

Demo
	- Create an S3 bucket
	- Upload a file using “AWS KMS Master-Key”
	- If you click on file details - it should say encrypted with KMS

Notes **
- If the KMS key is disabled, they won’t be able to do decrypted the file when you download it
- You can schedule key deletion (AWS recommends to wait for 7 days to verify whether the keys are still needed to decrypt)
- Uses envelop encryption
	- Practice of encrypting plaintext data with a data key, and then encrypting the data key under another key.

How does the encryption and decryption work
- How to implement Encryption
    - Create a KMS key aws kms create-key
    - Create a data key aws kms generate-data-key
        - Returns two things:
            - Plain text data key
            - Encrypted version of the data key (also known as CipherTextBlob)
    - Use the plain-text data key to encrypt the data
    - Throw away the plan-text data key and store the CIpherTextBlock along side of the encrypted data
- To decrypt
    - Use the decrypt api to decrypt the encrypted data by sending the cipher text blob data
    - This should return the plain text data key that we through away.
    - Use the plain text data key to decrypt

Reference: https://medium.com/faun/introduction-to-aws-kms-e87fffbf55f
