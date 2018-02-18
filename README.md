# terraform-aws-vpc

(https://img.shields.io/github/tag/pandao/editor.md.svg) ![]

This repository contains a [Terraform][] project that builds [Scenario 2: VPC
with Public and Private Subnets][scenario_two] from the [AWS documentation][].
It's from [this blog post][blog_post] describing how it all works and is
designed to give a working example which can the basis of something much more
complex.
Take a look at Git repository with TF Aws Modules [Terraform AWS Modules][], it contains a lot of good modules and examples.


![](https://nickcharlton.net/resources/images/aws_terraform_network_diagram.png)

The network diagram above is the best demonstration of what’s implemented:

- The private subnet is inaccessible to the internet (both in and out).
- The public subnet is accessible; just dependent on the configuration of the security groups. Elastic IPs can be associated with instances in here.
- Instances in the public subnet can access instances in the private subnet (also dependent on security groups) because they’re in the same VPC (this is enabled by the route tables).
- Routing is handled like this:
   - Private subnet is routed through the NAT instance.
   - Public subnet is routed directly to the internet gateway.


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
