# General
## High
- Tag VPC / EC2 / DB
- Delete unused resources
- <details>
    <summary>Configure access logging</summary>

    - VPC flow logs
    - ALB
    - API Gateway
    - CloudFront
    - WAF
    - DNS query log?
  </details>

- <details>
    <summary>Create CloudWatch Dashboard</summary>

    # Dashboard

    ## Service

    - 각 계층의 RED
        - Latency의 경우 avg와 p99를 모두 모니터링
        - CloudFront
        - API gateway
        - ALB
        - Lambda

    ## Infra

    - Capacity
        - Application / Node의 갯수
        - Target group healthy count
        - Desired와 current를 동시에 비교
    - Util
        - Network
        - Scaling의 기준이 되는 metric
            - CPU / memory
            - request

    ## Alarm

    - Configure alarms
  </details>
- <details>
    <summary>Check security group ingress</summary>

    - Delete 0.0.0.0/0
    - Modify well-known ports
      - 22
      - 3306
      - Other DB ports
  </details>
- Create VPC endpoints
- Apply HTTPS / CloudFront
- Enforce IMDS v2
- Ensure min 2 applications + Auto scaling
- Restart application & check health

## Medium
- Enable KMS key rotation
- Enable CloudTrail
- Check ALB listener rules

## Low
- Restrict unused egress
- Enable DNS query logging
- Enable GuardDuty
- Use SSM instead of Bastion

# CloudFront
- Enable WAF
- Enable caching

# API Gateway
- Enable caching
- Enable detailed metrics
- Enable X-Ray

# Secrets Manager
- Enable secret rotation

# EFS
- Check EFS access policy

# S3
- Enable versioning
- Configure intelligent-tiering
- Enforce HTTPS
- Enable KMS encryption

# Lambda
- Use arm64 processor
- Check hard-coded secret
- Enable X-Ray
- Enable code signing

# EC2
- Use custom AMI
- Enable detailed monitoring
- Install CloudWatch Agent
- Encrypt EC2 volume

# Container
- Enable Container Insights
- Enable logging
- Check API server endpoint access
- Enable scan on push
- Enable KMS encryption
- Enable tag immutability
- Check vulnerability

# RDS
- Enable encryption in transit
- Enable logging
- Enable KMS encryption
- Enable backup
- Enable PITR
- Create snapshot
- Turn on performance insights
- Enable enhanced monitoring
- Ensure multi-AZ
- Disable public access
- Turn on DevOps Guru

# DynamoDB
- Enable KMS encryption
- Enable PITR
- Create snapshot
- Enable contributor insights

# CodeCommit
- Enable KMS encryption
- Enable CodeGuru Reviewer