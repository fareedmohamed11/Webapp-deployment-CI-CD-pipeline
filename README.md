# project "ODC - ORANGE "
![Screenshot 2024-12-22 022854](https://github.com/user-attachments/assets/9bffd21d-2f0e-4f63-af6f-fd6ca6e879ff)



# WebApp Weather Pipeline Project 
![diagram-export-12-24-2024-2_08_07-AM](https://github.com/user-attachments/assets/8fccda63-9c4a-4aab-8c28-3cb692a42f1d)

## This project represents Version 1 of automating the deployment of a Python-based weather application using Docker, AWS EC2, Jenkins, and Ansible. Below is a breakdown of the work done, the tools used, and the project flow.

## Key Features
Application: A Python-based weather app, containerized with Docker.
Infrastructure: Two AWS EC2 Ubuntu instances configured to host the application.
Deployment Automation: Ansible manages EC2 configuration, sets up Docker, and deploys the application container.
Prerequisites
## Tools Required:

Git
Docker
AWS CLI
Jenkins
Ansible
## Accounts Required:

GitHub (for repository management)
Docker Hub (for image storage)
AWS Account (for EC2 instances)
## Credentials:

Jenkins credentials with Docker Hub username and token:
From manage jenkins >>> credentials 
![image](https://github.com/user-attachments/assets/9b0724c4-b237-47c6-9c1d-70e47d08cf22)

AWS credentials configured for the CLI.

## Steps to Setup
## 1. Initial Work on Local Machine
Code Handling:

Received the Python application code from the developer.
Created a Dockerfile to containerize the application.
Stages in Docker (as a description):

Set up a lightweight Python 3.9 base image.
Copied the application code into the container.
Installed the necessary dependencies (using requirements.txt).
Exposed port 5000 for the application.
Defined the command to run the Python application.
Repository Management:

Uploaded the Dockerized application to a private GitHub repository.
## 2. Jenkins Setup
Jenkinsfile:
A Jenkins pipeline was created with the following stages:
Clone the Code: Pull the application code from the private GitHub repository.
Build the Image: Build a Docker image from the Dockerfile.
Push the Image: Push the built Docker image to Docker Hub.
Run the Container: Test the container locally.
Trigger Ansible Playbook: Automate deployment on the EC2 instances.
## 3. AWS EC2 Instances
Setup:
Two Ubuntu instances were created using the AWS Management Console.

Manual SSH Access (Configured locally):
Copied the key file to the SSH directory:

```bash
نسخ الكود
sudo cp -rf /mnt/c/Users/aliam/Downloads/ansible1.pem ~/.ssh/id_ed25519
```

Accessed the instances:

```bash
نسخ الكود
ssh -i /home/ali/.ssh/id_ed25519 ubuntu@54.237.235.118
```
## 4. Ansible Configuration
Inventory File:
Contains details about the EC2 instances, including their IP addresses and the key pair for SSH authentication.

Playbook Tasks:
The playbook automates the following steps:

Updates and upgrades the packages on both EC2 instances.
Installs Docker and Git.
Clones the private GitHub repository on the instances.
Pulls the Docker image from Docker Hub.
Runs the Docker container on both instances.

## Project Flow
Clone the application repository.
Create a Dockerfile to containerize the application (details in the repository).
Push the Docker image to Docker Hub using Jenkins.
Use Ansible to configure the EC2 instances, pull the Docker image, and run the application automatically.
This setup represents a fully automated pipeline where the Python application code is deployed on AWS EC2 instances via containerization. The code and configurations are available in the GitHub repository.

![image](https://github.com/user-attachments/assets/f7fdb802-f664-4171-a749-7b2475c19b22)

----------------------------------------------------------------------











development process.
The file can be accessed under the name: 
## Output_images
-------------
## Acknowledgments
Special thanks to Instructor Ali Ayman for his continuous support and guidance throughout the project.
Additionally, heartfelt gratitude to Dhub and Orange for their contributions.
