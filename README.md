# terraform-aws-vpc

(https://img.shields.io/github/tag/pandao/editor.md.svg) ![]

This repository contains a [Terraform][] project that builds [Scenario 2: VPC
with Public and Private Subnets][scenario_two] from the [AWS documentation][].
It's from [this blog post][blog_post] describing how it all works and is
designed to give a working example which can the basis of something much more
complex.
Take a look at Git repository with TF Aws Modules [Terraform AWS Modules][], it contains a lot of good modules and examples.


![](https://nickcharlton.net/resources/images/aws_terraform_network_diagram.png)


## Usage

`terraform.tfvars` holds variables which should be overriden with valid ones.

### Plan

```
terraform plan -var-file terraform.tfvars

```

### Apply

```
terraform apply -var-file terraform.tfvars

```

### Destroy

```
terraform destroy -var-file terraform.tfvars

```


---
[Terraform]: http://terraform.io
[scenario_two]: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Scenario2.html
[AWS documentation]: http://aws.amazon.com/documentation/
[Terraform AWS Modules]: https://github.com/terraform-aws-modules
