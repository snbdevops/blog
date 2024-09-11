# Terraform Modules

-> **Route Module:** It resides in the main working directory of our terraform configuration. Its the entry point for your infrastructure definition.

example:
```
module "ec2"{
	source = "../modules/ec2"
}
```
-> **Child Module:** A module that has been called by another module is called child module.

example: the modules where the actual resource creation code is written are child modules like, ../modules/ec2 , ../modules/vpc , etc...


-> **Example of using Output**

Lets Say, I have a module to create an EC2 Instance. Now, I want to use it and create an EC2 and I also want to create an EIP and attach it to the instance. Here, creating an attaching an EIP to the will require us to create an child module Output.

Example: 
1. modules.tf
```
resource "aws_instance" "myec2"{
  ami = var.image_id
  instance = var.instance_type
}

output "instance_id"{
  value = "aws_instance.myec2.id"
}
```
2. main.tf
```
module "ec2" {
  source = "../modules/ec2"
}

resource "aws_eip" "lb" {
  instance = "module.ec2.instance_id"
  domain  = "vpc"
}
```

