# K10-Ansible-Install-Configure

***Status:** Work-in-progress. Please create issues or pull requests if you have ideas for improvement.*

# **Fully automated Kasten K10 installation and initial basic configuration with Ansible**
Example of using Ansible to automate the installation and initial Kasten K10 configuration including:
* EULA agreement
* Location Profile creation
* Policy preset samples creation
* Policy creation to protect cluster-wide resources

## Summary
This projects demostrates the process of installing and configurig Kasten K10 using Ansible for fully automation of this process.  

All the automation is done using Ansible playbooks and leveraging the [Kasten K10 API](https://docs.kasten.io/latest/api/cli.html).

## Disclaimer
This project is an example of an deployment and meant to be used for testing and learning purposes only. Do not use in production. 


# Table of Contents

1. [Prerequisites](#Prerequisites)
2. [Installing Kasten with Ansible](#Installing-Kasten-with-Ansible)



## Prerequisites
To run this project you need to have some software installed and configured: 
1. A workstation with the next tools installed:
	- Kubectl
	- Kubernetes Collection for Ansible
	- Helm
1. A working [Ansible installation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).
1. A working Kubernetes cluster.  In this project, we will provide the Ansible Playbooks to complete the following tasks:
	- Installing Kasten K10
	- EULA agreement
	- Location Profile creation
	- Policy preset samples creation
	- Policy creation to protect cluster-wide resources


## Installing Kasten with Ansible
* Installing Kasten with Ansible in Azure AKS: [Ansible_K10AKS/README.md](Ansible_K10AKS/README.md)
* Installing Kasten with Ansible in Amazon EKS: [Ansible_K10EKS/README.md](Ansible_K10EKS/README.md)
* Installing Kasten with Ansible in Google GKE: [Ansible_K10GKE/README.md](Ansible_K10GKE/README.md)
* Installing Kasten with Ansible in Tanzu Kubernetes Grid: [Ansible_K10TKG/README.md](Ansible_K10TKG/README.md)