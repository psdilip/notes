# AWS Config

- Will record your configuration changes over time
- Stores configuration data in S3
- AWS Config can help you answer these questions
    - Is there unrestricted SSH access to my security groups?
    - Do my buckets have any public access?
    - How has my ALB configuration changed over time?
- You can setup any SNS alerts for any changes made
- Can be a per region service or can be aggregated from regions and accounts
- Comes out of box with 75 rules made for you
- You can also make customer config rules within Lambda
- Rules are trigged via following
    - For each config change
    - And/Or: at regular time intervals
- Pricing
    - No free tier
    - $2 per active rule per region per month
    - After 10 rules, the code gets reduced