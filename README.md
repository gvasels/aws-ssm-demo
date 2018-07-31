# aws-ssm-demo
This repository is a tutorial of AWS Systems Manager, focusing on Actions the service is able to perform. A future iteration will be in the works to tie in all the features of Systems Manager..

## Prerequisites
1) An AWS Account
2) A IAM user that can spin up / tear down EC2 instances, execute actions in Systems Manager, and create EC2 IAM roles to access AWS Systems Manager.
## Tutorial Set up
We will be provisioning instances for the tutorial. No SSH access will be granted to any of these instances.

1) Create EC2 Service Role to access EC2 Systems Manager
- IAM role name: ec2-ssm-demo
2) Spin up 2 t2.medium Windows Instances
- GO to the EC2 Console
- Click Launch Instance
- Select Windows Server 2016 Base AMI that appears in the Quick Start Tab
- In Configure Instance Details, select Number of Instances: 2, and IAM role: ec2-ssm-demo2
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
3) Spin up 2 t2.micro Linux Instances
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

The Run Command is the heart and soul of Systems Manager. It allows you to remotely manage your EC2 instances without having to SSH into them. You are effectively applying operations on your instances via this tool, and it is the foundation to ensure consistency across your EC2 fleet. The following blog post goes into detail about the benefits of using the Run Command over SSH and shows an example of restarting a Docker container: https://aws.amazon.com/blogs/aws/manage-instances-at-scale-without-ssh-access-using-ec2-run-command/

The Run Command executes Documents. TODO: Define Documents.

Let's Run a PowerShell script to install a web server.
- Inside Run Command. click on Run a Command
- Find the AWS-RunPowerShellScript run command.
- Targets: Specify targets by specifying a tag (K: Name, V: windows-ssm)
- Commands: 
``` Install-WindowsFeature -name Web-Server -IncludeManagementTools```



## Patch Manager

## Maintenance Windows
## State Manager
## Automation
