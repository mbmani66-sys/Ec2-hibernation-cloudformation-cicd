EC2 Hibernation using AWS CloudFormation & GitHub Actions CI/CD
Project Overview

This project demonstrates how to provision an Amazon EC2 instance configured for hibernation using AWS CloudFormation and automate the deployment with GitHub Actions.

The infrastructure is defined as code (IaC), enabling repeatable and version-controlled deployments directly from GitHub.

CI/CD Workflow
Developer pushes code to GitHub.
GitHub Actions workflow starts automatically.
AWS credentials are loaded from GitHub Secrets.
CloudFormation deploys the VPC stack.
CloudFormation deploys the EC2 stack.
The workflow waits for the instance to become available.
The EC2 instance ID is retrieved from the CloudFormation outputs.
AWS CLI issues a hibernate command to the instance.
GitHub Secrets

Configure the following repository secrets:

AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
Required IAM Permissions

The IAM user used by GitHub Actions should have permissions to manage:

AWS CloudFormation
Amazon EC2
IAM (for the instance role)

Common managed policies include:

CloudFormationFullAccess
AmazonEC2FullAccess
IAMFullAccess
