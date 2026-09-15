# AWS EC2 with Terraform

A small Terraform project for bringing up a public EC2 instance inside its own VPC. I kept the layout simple enough to review quickly, but it includes the network pieces I would expect around the instance rather than relying on the default VPC.

## What it creates

- VPC and public subnet
- Internet gateway and default route
- Security group with HTTP open and SSH restricted to a supplied CIDR
- Amazon Linux 2023 EC2 instance
- Instance ID and public IP outputs

## Use

Copy the example values and replace the SSH CIDR with your own public IP.

```bash
cp terraform.tfvars.example terraform.tfvars
terraform init
terraform fmt -check
terraform validate
terraform plan
terraform apply
```

When finished:

```bash
terraform destroy
```

`terraform.tfvars` and state files are ignored. The example file is safe to keep in the repository.
