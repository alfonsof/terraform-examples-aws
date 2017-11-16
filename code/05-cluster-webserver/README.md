# Terraform Cluster Web Server example

This folder contains a cluster of web servers example of a Terraform file (https://www.terraform.io/).
This Terraform file deploys a cluster of web servers in Amazon Web Services (AWS) using EC2 and Auto Scaling, as well as a load balancer using ELB.
The cluster of web servers returns "Hello, World" for the URL `/`. The load balancer listens on port 80.

## Requirements

* You must have [Terraform](https://www.terraform.io/) installed on your computer. 
* You must have an [Amazon Web Services (AWS) account](http://aws.amazon.com/).

This code was written for Terraform 0.10.x.

## Using the code

Configure your AWS access keys

Validate the changes:

```
terraform plan
```

Deploy the changes:

```
terraform apply
```

Test the cluster of web servers. When the `apply` command completes, it will output the DNS name of the load balancer.

```
curl http://(elb_dns_name)/
```

Clean up the resources created when you have finished:

```
terraform destroy
```