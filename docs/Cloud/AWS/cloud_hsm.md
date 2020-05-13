# Cloud HSM (Hardware security Module)
  - A physical device used for secure key storage and management
  - Can be placed in Multi-Az and clustered(Load Balancer and Replicated Keys)
- Integrates with your vpc
- Need to use industry standard api to interact with CloudHSM
- Compliance -> FPS 140-2 Level 3
- You can use HSM to connect to your on-premise data center via VPN or Direct Connect

References:
- https://medium.com/faun/introduction-to-aws-kms-e87fffbf55f
- https://lobster1234.github.io/2017/09/29/aws-kms-envelope-encryption/
