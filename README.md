# Terraform AWS VPC Project

This project demonstrates creating a VPC in AWS using Terraform with a local backend.

## Features
- A VPC with public and private subnets.
- An Internet Gateway and NAT Gateway for routing.
- Elastic IP and security groups for web servers.

## Backend
This project uses a **local backend** to store the Terraform state file. By default, the state file is stored in the project directory as `terraform.tfstate`.

### Important Notes:
- **Security**: Ensure that the Terraform state file is kept secure. It contains sensitive information about the resources created (e.g., resource IDs, IP addresses). Do not share it publicly.
- **Remote Backend**: For team use or production environments, consider switching to a **remote backend** like AWS S3 or HashiCorp's Terraform Cloud for better state management and collaboration.

## How to Use

1. Clone the repository to your local machine:

   `git clone https://github.com/<your-username>/terraform-aws-vpc.git`

   Then navigate to the project directory:

   `cd terraform-aws-vpc`

2. Customize the `terraform.tfvars` file with your specific settings. This file contains configuration values like your AWS region and CIDR blocks. 

   You can start by copying the example file:

   `cp terraform.tfvars.example terraform.tfvars`

   Edit `terraform.tfvars` with your preferences (e.g., setting your AWS region or VPC CIDR block).

3. Initialize Terraform by running the following command. This will download necessary provider plugins and set up the backend:

   `terraform init`

4. Once Terraform is initialized, review the execution plan to see what changes Terraform will make in your environment. This helps ensure that it matches your expectations:

   `terraform plan`

5. Apply the configuration to create the infrastructure. Terraform will show you the changes and ask for confirmation before proceeding:

   `terraform apply`

6. When you’re done and want to tear down the infrastructure (to avoid ongoing charges), run:

   `terraform destroy`

   This will remove all the resources created by your Terraform configuration.

## Notes
- The state file is stored locally for simplicity. Avoid sharing it publicly.
- If you're working in a team, consider using a remote backend such as AWS S3 or Terraform Cloud.
- Be mindful of AWS costs when provisioning resources such as NAT Gateways, Elastic IPs, and VPCs.
- If you encounter any issues, check the AWS console for error details or permissions issues.

## Resources
- [Terraform Documentation](https://www.terraform.io/docs)
- [AWS VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/)
