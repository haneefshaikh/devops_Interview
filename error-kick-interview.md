# DevOps Interview Qustions From Error-Kick Round 1.

## LINUX

### 1. How do you check for multiple processes currently running in Linux?

`ps -ef | grep <PROCESS_NAME/SERVICE_NAME`>` also you can use `TOP` command to check the system process.


### 2. What are soft links and hard links?

`HARD LINK`
```
A hard link is a reference to a file on the file system that points to the same inode (index node) as the original file. 
When you create a hard link, you create another name for the same file, which means that both the original file and the hard link have the same contents and metadata
```
`SOFT LINK`
```
A soft link, also known as a symbolic link or symlink, is a special type of file that points to another file or directory on the file system. 
A soft link acts as a shortcut or alias to the original file or directory, which means that any changes made to the original file or directory will also affect the soft link.
```

### 3. How do you identify soft links and hard links?
```
you can use the "ls -ltr" command in Unix-based operating systems.
you will see detailed information about each file, including its type, permissions, owner, and group. 
The first character in the output indicates the type of file.

If the first character is "l", the file is a soft link.

If the first character is "-", the file is a hard link.
```

## SHELL SCRIPTING

### 1. Write a shell script to take an EBS snapshot.
 
### 2. What does 'set -x' do in shell scripting?
 
### 3. What type of shell scripting have you written?


## ANSIBLE

### 1. What did you achieve using Ansible?

### 2. What things do we need to consider while creating an Ansible inventory?

### 3. What is Ansible Vault, and how can I use Vault content in the code?

### 4. What Ansible modules do you know about?

### 5. Do you knows about Ansible Tower?


## DOCKER

### 1. How do I check the size of a specific docker image and entire container?

- to check the size of specific docker image : `docker images -q <image_name>`
- to check the size of entire container : `docker ps --size`
 
### 2. what is the difference between dockerfile and docker-compose file ?
```
Dockerfile is used to create Docker images, while Docker Composr is used to manage multiple Docker containers.
```

### 3. Write a Dockerfile to build a Python application image. What instructions should I take care of while writing the file?

`FROM`: It specifies the based image to use for a Docker image.

`RUN`: Executes commands in Docker image, such as installing packages, updating the system, or setting environment variables.

`COPY` and `ADD`: Copy files or directories into the Docker Image from the local file system or remote URLs.

`WORKDIR`: Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY, or ADD commands that follow it.

`EXPOSE`: Specifies which ports the Docker container will listen on at runtime.

`CMD` and `ENTRYPOINT`: Define the command that will run when the container starts

`ENV`: Sets environment variables in Docker image.

`ARG`: Defines variable that can be passed at build time using the '--build arg' flag.

`LABEL`: Adds metadata to the Docker image, such as the maintainer, version, or description.


## GIT

### 1. What is Git bisect, and how do you use it?
 
### 2. What is a merge conflict in Git?


## JENKINS

### 1. What is the global tool configuration block in Jenkins?

### 2. do you knows about Webhook?


## AWS

### 1. I have a Flipkart application deployed on a 2-node EC2 machine with auto-scaling on when the load threshold exceeds 70%. In this scenario, when a third instance is launched, how does the new EC2 machine know about the Flipkart application that needs to be run?

### 2. What is VPN peering, what is its purpose, and how do you deploy it?
 
### 3. What are bastion nodes and NAT instances in AWS?


## TERRAFORM

### 1. What is the 'terraform.state.lock' file?
 
### 2. If I have created resources manually on my AWS account, what steps do I need to take to write Terraform code for my existing resources?


## KUBERNETES

### 1. What is deployment, and what is its use?

### 2. What is the difference between deployment and StatefulSets?

### 3. What kind of security measures have you implemented in Kubernetes?

### 4. How do I deploy an EKS cluster in AWS?

### 5. Write a Kubernetes code to create an Nginx pod.


## PYTHON

### 1. What type of scripts have you written in Python?
 
### 2. Write a Python script to retrieve the even and odd numbers from 1 to 100.

