terraform-aws-ec2-instance
==========================

Terraform module to create EC2 instance. Credits to https://github.com/terraform-aws-modules/terraform-aws-ec2-instance.


Usage
-----

```hcl
module "t1" {
    source = "Smartbrood/ec2-instance/aws"
    name                 = "t1"
    count                = "1" 
    ami                  = "${data.aws_ami.ubuntu1604.id}"
    instance_type        = "t2.micro"
    key_name             = "${var.key_name}"
    iam_instance_profile = "${var.profile_name}"
    subnet_id            = "${var.subnet_id}"

    vpc_security_group_ids      = ["${var.security_group_id}"]
    associate_public_ip_address = false
    monitoring                  = false

    tags = {
             Name = "t1"
             Terraform = "true"
    }
}
```


Authors
-------

Module managed by [Smartbrood LLC](https://github.com/Smartbrood).


License
-------

Apache 2 Licensed. See LICENSE for full details.
