=============================================
ASSIGNMENT USING TERRAFORM, ANSIBLE, JENKINS, DOCKER
=============================================
============
DESCRIPTION:
============
terraform-jenkins:
* This module includes creation of necessary resources like "VPC", "Subnet", "Firewall-rules", "Service-Account", "Jenkins-VM".

terraform-desktop:
* This module includes creation of "Desktop-VM" utilizing the resources created in "terraform-jenkins"

Dockerfile:
* This file sets-up a runtime environment for a "Docker-Container" to perform all the tasks like running "Terraform", running "Ansible-Playbook" etc.

Playbook: 
* This has all the "Packages" and "Softwares" to be installed in "Desktop-VM"

Jenkinsfile:
* This Jenkinsfile has the "Pipeline" which includes different stages to be performed to "Create" and "Configure" the "Desktop-VM".

STEP1: Creating Infrastructure to run Jenkins-server(master)
* Clone terraform code from GitHub: git clone https://github.com/summu97/ASSESMENT.git

STEP2: Build docker-image
* docker build -t docker-desktop:v1 /Path/to/Dockerfile.
* Push image to Docker Hub or any Artifactory repository.

STEP3: Configuring Jenkins-server
* Login to Jenkins-server, get password to login to Jenkins-UI.
* Now login to Jenkins-UI and configure Jenkins to use Docker as agent and get pipeline from "Jenkinsfile".

NOTE:
* Plugin required: Docker

STEP4: Trigger the build
* Start the build by providing appropriate action(apply, destroy) to trigger terraform.
  



