# ansible
EC2 Cluster deployment with ansible

This set of playbooks will help you deploy your cluster on AWS

It has 3 parts:

First, is deploying the instances (ec2deploy.yml)
  1) Edit the file ec2deploy.yml and add your variables
  2) Create environment variables named AWS_ACCESS_KEY and AWS_SECRET_KEY
  3) Run the playbook
  * You can read more about ec2 deployment with ansible at https://docs.ansible.com/ansible/2.6/modules/ec2_module.html 
  
2nd part is the ssh key installation. It will run a set of commands and enable public_key authenticaton to the master server.
  1) Add the IPs of newly created instances to hosts file ( You can get all the private IPs with the command inide deployment/getIP )
  2) Run the playbook with command "ansible-playbook sshsetuo.yml --ask-pass
  
3rd part is my custom deployment of WordPress site. It can be edited however you want. 
It is made for instances inside the subnet, so the first part inside install/tasks/main.yml is for configuring networking. 
Add the commands and packages you want to install and run it like any other ansible-playbook

### WORK IN PROGRESS ###
