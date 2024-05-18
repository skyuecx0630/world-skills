# General
## High
- Tag VPC / EC2 / DB
- Delete unused resources
- Configure access logging
- Create CloudWatch Dashboard
- Check security group ingress
- Create VPC endpoints
- Apply HTTPS / CloudFront
- Ensure min 2 applications + Auto scaling
- Check application health
- Enforce IMDS v2

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