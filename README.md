# aws-eks

This repo contains terraform modules to create EKS cluster in aws.

Below is structure of our repo and purpose of the file:

1. **vpc.tf** : in this we are creating public and private subnets and to define the range we need to edit **terraform.tfvars** file.
```vpc_cidr = "10.0.0.0/16"
private_subnet_ips = ["10.0.1.0/24", "10.0.2.0/24", "10.0.3.0/24"]
public_subnet_ips = ["10.0.4.0/24", "10.0.5.0/24", "10.0.6.0/24"]
```

We need to change these variable if subnet and vpc cidr needs to change.

2. **backend.config**: this file contains S3 bucket information which will help us to store the terraform state file.
3. **eks-cluster.tf**: in this we are creating cluster, defining eks version and worker node groups.
4. **outputs.tf**: Here we define after creating cluster for which variable we need name or output of the like eks cluster name.

To apply the changes or creating the new cluster. We need to run below commands

```
terraform init -backend-config=backend.config   
```
```
terraform plan
```
Once Terraform plan is finished , review it and apply the changes with following command:

```
terraform apply
```
once it asks for confirmation type yes to continue applying the changes.





































