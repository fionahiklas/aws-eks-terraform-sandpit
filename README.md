# aws-eks-terraform-sandpit

## Overview

Experiments using the Terraform EKS module based initially on this 
[tutorial](https://medium.com/devops-mojo/terraform-provision-amazon-eks-cluster-using-terraform-deploy-create-aws-eks-kubernetes-cluster-tf-4134ab22c594)


## Quickstart

* Install the prerequisites
* Run `terraform -chdir=infrastructure init -var-file=../tmp/test.tfvars`
* Run `terraform -chdir=infrastructure plan -var-file=../tmp/test.tfvars`
* Run `terraform -chdir=infrastructure apply -var-file=../tmp/test.tfvars`



## Prerequisites

### Terraform

* Installed on MacOS using the following command

```
brew tap hashicorp
brew install hashicorp/tap/terraform
```

### AWS/EKS CLIs

* On MacOS using brew again

```
brew install awscli eksctl
```


### Kubernetes tools

* On MacOS

```
brew install kubectl kubectx
```


## Notes

### Setting up AWS CLI

* Created access key using web console for AWS
* Creating configuration using the following command

```
aws configure --profile fiona
```

* Asks the following questions

```
AWS Access Key ID [None]: <enter key ID>
AWS Secret Access Key [None]: <enter secret key>
Default region name [None]: eu-west-2
Default output format [None]: json
```


### Querying AZs

On AWS CLI

```
aws --profile fionahiklas ec2 describe-availability-zones
```



### Trying to run terraform

Setup a `tmp` directory (which will be ignored by git) with the `test.tfvars` file containing

```
aws_access_key = "<access key>"
aws_secret_key = "<secret_key>"

region                   = "eu-west-2"
availability_zones_count = 1

project = "TestCluster"

vpc_cidr         = "10.0.0.0/16"
subnet_cidr_bits = 8
```

Running the following command from the root of the cloned repo

```
terraform -chdir=infrastructure plan -var-file=../tmp/test.tfvars
```

This will produce ALOT of output



## References

### Terraform

* [Terraform Home Page](https://www.terraform.io/downloads)
* [EKS Module](https://registry.terraform.io/modules/terraform-aws-modules/eks/aws/latest)
* [Use Terraform modules from the registry](https://learn.hashicorp.com/tutorials/terraform/module-use?in=terraform/modules)
* [State backend configuration](https://www.terraform.io/language/settings/backends/local)
* [Terraform variables](https://www.terraform.io/language/values/variables)


### AWS

* [Homebrew awscli](https://formulae.brew.sh/formula/awscli)
* [Connect to EKS cluster](https://aws.amazon.com/premiumsupport/knowledge-center/eks-cluster-connection/)
* [Provision AWS EKS with terraform](https://medium.com/devops-mojo/terraform-provision-amazon-eks-cluster-using-terraform-deploy-create-aws-eks-kubernetes-cluster-tf-4134ab22c594)
* [List AWS CLI profiles](https://superuser.com/questions/1260311/is-there-a-way-to-list-available-configured-aws-cli-profiles)
* [AWS CLI describe AZs](https://docs.aws.amazon.com/cli/latest/reference/ec2/describe-availability-zones.html)


### Kubernetes

