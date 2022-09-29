# aws-eks-terraform-sandpit

## Overview

Experiments using the Terraform EKS module


## Variables

* aws_access_key
* aws_secret_key
* availability_zones_count
* project - used for AWS resource naming
* region - specifies AWS region to use
* vpc_cidr
* subnet_cidr_bits

## Prerequisites

### Terraform

* Installed on MacOS using the following command

```
brew tap hashicorp
brew install hashicorp/tap/terraform
```

### AWS Cli

* On MacOS using brew again

```
brew install awscli
```


### Kubernetes tools

* On MacOS

```
brew install kubectl kubectx
```


## References

### Terraform

* [Terraform Home Page](https://www.terraform.io/downloads)
* [EKS Module](https://registry.terraform.io/modules/terraform-aws-modules/eks/aws/latest)
* [Use Terraform modules from the registry](https://learn.hashicorp.com/tutorials/terraform/module-use?in=terraform/modules)
* [State backend configuration](https://www.terraform.io/language/settings/backends/local)

### AWS

* [Homebrew awscli](https://formulae.brew.sh/formula/awscli)
* [Connect to EKS cluster](https://aws.amazon.com/premiumsupport/knowledge-center/eks-cluster-connection/)
* [Provision AWS EKS with terraform](https://medium.com/devops-mojo/terraform-provision-amazon-eks-cluster-using-terraform-deploy-create-aws-eks-kubernetes-cluster-tf-4134ab22c594)


### Kubernetes

