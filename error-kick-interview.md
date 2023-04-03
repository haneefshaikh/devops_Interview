# DevOps Interview Qustions

## LINUX

### 1. How do you check for multiple processes currently running in Linux?

`ps -ef | grep <PROCESS_NAME/SERVICE_NAME>` also you can use `TOP` command to check the system process.


### 2. What are soft links and hard links?

`HARD LINK`

A hard link is a reference to a file on the file system that points to the same inode (index node) as the original file. 
When you create a hard link, you create another name for the same file,
which means that both the original file and the hard link have the same contents and metadata

`SOFT LINK`

A soft link, also known as a symbolic link or symlink,
is a special type of file that points to another file or directory on the file system. 
A soft link acts as a shortcut or alias to the original file or directory,
which means that any changes made to the original file or directory will also affect the soft link.


### 3. How do you identify soft links and hard links?

you can use the `ls -ltr` command in Unix-based operating systems.
you will see detailed information about each file, including its type, permissions, owner, and group. 
The first character in the output indicates the type of file.

If the first character is `l`, the file is a soft link.

If the first character is `-`, the file is a hard link.


## SHELL SCRIPTING

### 1. Write a shell script to take an EBS snapshot.
```
#!/bin/bash

# Set your AWS region and the EBS volume ID to snapshot
region="us-west-2"
volume_id="vol-xxxxxxxxxxxxxx"

# Get the current date and time in YYYY-MM-DD-HH-MM format
timestamp=$(date +%Y-%m-%d-%H-%M)

# Create a new EBS snapshot with a description that includes the timestamp
aws ec2 create-snapshot --volume-id $volume_id --description "Snapshot taken at $timestamp" --region $region
```

### 2. What does 'set -x' do in shell scripting?

set -x is a command that enables the shell's debugging mode. 
When this command is run in a shell script, the shell will print each command before executing it, 
along with the values of any variables or parameters used in that command.

### 3. What type of shell scripting have you written?


## ANSIBLE

### 1. What did you achieve using Ansible?

### 2. What things do we need to consider while creating an Ansible inventory?

`Server information`: The inventory should contain information about the servers, including their IP addresses, domain names, and hostnames.

`Grouping`: Servers can be grouped based on their functionality, such as web servers, database servers, and application servers. 
You can also group servers based on their location or environment, such as production or development.

`Variables`: Variables can be used to define specific settings for each server, such as the operating system, available storage, and CPU.

`Authentication`: You will need to define how Ansible will authenticate with the servers, including the username and password or SSH keys.

`YAML syntax`: Ansible inventories are written in YAML syntax, so you will need to have a good understanding of this format.

### 3. What is Ansible Vault, and how can I use Vault content in the code?

Ansible Vault is a feature of Ansible that allows you to encrypt sensitive data, 
such as passwords, SSH keys, and other credentials, that are needed by Ansible playbooks.

To use Vault content in your code, you first need to create an encrypted file using the ansible-vault command. 
`ansible-vault create mysecrets.yml`
You can create a new file or encrypt an existing file. Once the file is encrypted, 
you can add it to your playbook just like any other file. 


### 4. What Ansible modules do you know about?

`apt/yum`: for installing or removing packages.

`copy/template`: for copying or templating files and directories on remote systems.

`file`: for managing files and directories, such as creating or deleting them, setting permissions and ownership.

`service`: for managing services on remote systems, such as starting or stopping them, enabling or disabling them, and so on.

`user/group`: for managing users and groups on remote systems, such as creating or deleting them, adding or removing them from groups, and so on.

`command/shell/script`: for running commands or scripts on remote systems, either as a single command or a series of commands.

`cron`: for managing cron jobs on remote systems, such as creating or deleting them, modifying their schedule, and so on.

`docker_container`: for managing Docker containers on remote systems, such as starting or stopping them, creating or deleting them, and so on.

`ec2`: for managing Amazon Web Services (AWS) EC2 instances, such as starting or stopping them, creating or deleting them, and so on.


### 5. Do you knows about Ansible Tower?

Ansible Tower is the enterprise version of Ansible. It allows sysadmins to deploy all of the benefits of Ansible at scale.


## DOCKER

### 1. How do I check the size of a specific docker image and entire container?

- to check the size of specific docker image : `docker images -q <image_name>`
- to check the size of entire container : `docker ps --size`
 
### 2. what is the difference between dockerfile and docker-compose file ?

Dockerfile is used to create Docker images, while Docker Composr is used to manage multiple Docker containers.


### 3. Write a Dockerfile to build a Python application image. What instructions should I take care of while writing the file?

`FROM`: It specifies the based image to use for a Docker image.

`RUN`: Executes commands in Docker image, such as installing packages, updating the system, or setting environment variables.

`COPY` and `ADD`: Copy files or directories into the Docker Image from the local file system or remote URLs.

`WORKDIR`: Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY, or ADD commands that follow it.

`EXPOSE`: Specifies which ports the Docker container will listen on at runtime.

`CMD` and `ENTRYPOINT`: Define the command that will run when the container starts

`ENV`: Sets environment variables in Docker image.

`ARG`: Defines variable that can be passed at build time using the `--build arg` flag.

`LABEL`: Adds metadata to the Docker image, such as the maintainer, version, or description.


## GIT

### 1. What is Git bisect, and how do you use it?

The git bisect command is a powerful tool that quickly checks out a commit halfway between a known good state and a known bad state 
and then asks you to identify the commit as either good or bad. 


### 2. What is a merge conflict in Git?

A merge conflict in Git occurs when two or more branches have made changes to the same file, 
and Git is unable to automatically determine which changes should take precedence. 
When you try to merge these branches, 
Git will notify you of the conflict and ask you to resolve it manually.


## JENKINS

### 1. What is the global tool configuration block in Jenkins?

Its allows administrators to configure tools that are required for the build process,
 such as JDK installations, build tools like Maven or Gradle, and source control management tools like Git or Subversion. 
This configuration block is global, which means that the settings apply to all Jenkins jobs on the system.

### 2. do you knows about Webhook?

A webhook is a mechanism for one application to automatically trigger an action in another application when a certain event occurs. 
Webhooks are commonly used to integrate different systems and automate workflows.


## AWS

### 1. I have a Flipkart application deployed on a 2-node EC2 machine with auto-scaling on when the load threshold exceeds 70%. In this scenario, when a third instance is launched, how does the new EC2 machine know about the Flipkart application that needs to be run?

### 2. What is VPN peering, what is its purpose, and how do you deploy it?

VPN peering is a technique used to connect two or more VPNs together, 
allowing users to access resources in multiple networks.

The purpose of VPN peering is to provide secure and private communication between multiple VPNs, 
making it easier for users to access resources that are distributed across different networks.

### 3. What are bastion nodes and NAT instances in AWS?

A bastion node, also known as a jump server, 
is a special-purpose instance that is used to securely access resources in a private subnet from the internet. 
It acts as a gateway between the public and private subnets

A NAT instance is used to enable instances in a private subnet to communicate with the internet or other AWS services.


## TERRAFORM

### 1. What is the 'terraform.state.lock' file?

The terraform.state.lock file is a lock file that is created by Terraform when it runs a state operation.

When Terraform performs an operation that modifies the state file, 
such as terraform apply or terraform destroy, it creates a lock file named terraform.state.lock in the same directory as the state file

### 2. If I have created resources manually on my AWS account, what steps do I need to take to write Terraform code for my existing resources?

you can use the `terraform import` command to import the existing resources into your Terraform configuration.


## KUBERNETES

### 1. What is deployment, and what is its use?

### 2. What is the difference between deployment and StatefulSets?

### 3. What kind of security measures have you implemented in Kubernetes?

### 4. How do I deploy an EKS cluster in AWS?

### 5. Write a Kubernetes code to create an Nginx pod.


## PYTHON

### 1. What type of scripts have you written in Python?
 
### 2. Write a Python script to retrieve the even and odd numbers from 1 to 100.
```
# Retrieve even and odd numbers from 1 to 100

num = 100

for i in range(num):
    if i % 2 == 0:
        print("Even numbers: ", i)
    else:
        print("Odd numbers: ", i)
```
