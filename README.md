# ansible createEC2 dynamicInventry Deploy Application

Usually Ansible require an inventory file to find out on which machine it should work.

If you work with AWS, most probably you are using ASG, and your inventory varies with scale in and out instances in response to the demands. So static inventory will not work with your needs. You need to track the target hosts automatically.

To get around this problem, we can make use of Ansible’s ability to populate an in-memory inventory (dynamic inventory), using the add_host module, with information it generates while creating new instances.

## Overview

In this demo, we will be provisioning the following :

1. Provision an SSH keypair, security groups and EC2 instance through Ansible.
2. Retrieve the IP Address using register module and setup dynamic inventory using add_host module.
3. Deploying an application.

## Prerequisite

1. Access key and secret key for AWS IAM user with administrator access.
2. Install Ansible on your machine.

To working with AWS dynamic inventory, we need boto3 and botocore python modules.

First, install python2 if you haven’t installed it yet.

>> yum install -y python2

Install “boto3”

>> pip2 install  boto3

## Usage

1. Clone the repository using the below command

```
git clone https://github.com/jebincvarghese/Ansible-Dynamic-Inventory-Of--Autoscaling-EC2.git
```
2. 
```
cd ansible_ec2-dynamic-inventry/
```

3. Make the required changes in files for variables -aws_ec2.var and website.vars

4. Finally, you can run the ansible playbook using the command,
```
 ansible-playbook main.yml
```

## Result

Now our application has been depolyed in 2 EC2 instances and we can visit this using the public IP or domain name.



