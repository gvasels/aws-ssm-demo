# aws-ssm-demo
This repository is a tutorial of AWS Systems Manager, focusing on Actions the service is able to perform.

## Prerequisites
1) An AWS Account
2) A IAM user with EC2 and SSM permissions
## Tutorial Set up
We will be provisioning instances for the tutorial. No SSH access will be granted to any of these instances.

1) Spin up 2 t2.medium Windows Instances
- GO to the EC2 Console
- Click Launch Instance
- Select Windows Server 2016 Base AMI that appears in the Quick Start Tab
- In Configure Instance Details, select Number of Instances: 2
- Click through instance configuration and Storage. If the default VPC has not b
een deleted on your account, it will automatically set up the instances in a pub
lic subnet in the default VPC, with a public IP.
- Add a tag with Key of Name and Value of windows-ssm
- Create a security group with the name webserver-public, and allow Type HTTP, p
ort 80, on 0.0.0.0/0
- Before clicking Launch Instance, select proceed without a key pair, and check
the acknowledgement that you will not be able to connect to hte instance unless
you know password on the AMI.
- Launch the Instances
2) Spin up 2 t2.micro Linux Instances
- GO to the EC2 Console
- Click Launch Instance
- Select Amazon Linux 2 AMI that appears in the Quick Start Tab
- In Configure Instance Details, select Number of Instances: 2
- Click through instance configuration and Storage. If the default VPC has not been deleted on your account, it will automatically set up the instances in a public subnet in the default VPC, with a public IP.
- Add a tag with Key of Name and Value of linux-ssm
- Select the  webserver-public security group from the existing list
- Before clicking Launch Instance, select proceed without a key pair, and check the acknowledgement that you will not be able to connect to hte instance unless you know password on the AMI.
- Launch the instances
## The Run Command
In this section, we will look into what the Run Command is, and will install web servers onto our 4 provisioned instances.


## Patch Manager

## Maintenance Windows
## State Manager
## Automation
