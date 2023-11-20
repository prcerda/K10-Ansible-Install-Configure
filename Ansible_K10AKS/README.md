***Status:** Work-in-progress. Please create issues or pull requests if you have ideas for improvement.*

# **Fully automated Kasten K10 installation and initial basic configuration with Ansible**
Example of using Ansible to automate the installation and initial Kasten K10 configuration in **Azure Kubernetes Service (AKS)**, including:
* EULA agreement
* Location Profile creation
* Policy preset samples creation
* Policy creation to protect cluster-wide resources
* Kanister Blueprints creation for MongoDB and PostgreSQL app-consistent backups
* Kanister BlueprintBinding creation for automatic use of Blueprint (app fingerprinting)

## Summary
This projects demostrates the process of installing and configurig Kasten K10 using Ansible for fully automation of this process.  

All the automation is done using Ansible playbooks and leveraging the [Kasten K10 API](https://docs.kasten.io/latest/api/cli.html).

## Disclaimer
This project is an example of an deployment and meant to be used for testing and learning purposes only. Do not use in production. 


# Table of Contents

1. [Prerequisites](#Prerequisites)
2. [Installing Kasten with Ansible](#Installing-Kasten-with-Ansible)
3. [Variables](#Variables)

## Prerequisites
To run this project you need to have some software installed and configured: 
1. A workstation with the next tools installed:
	- Kubectl
	- Kubernetes Collection for Ansible
	- Helm
	- Kubeconfig file configured and kubectl context selected	
	- azure cli 
1. A working [Ansible installation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).
1. A working Kubernetes cluster.  In this project, we will provide the Ansible Playbooks to complete the following tasks:
	- Installing Kasten K10
	- EULA agreement
	- Location Profile creation
	- Policy preset samples creation
	- Policy creation to protect cluster-wide resources


## Installing Kasten with Ansible
In order to run the Ansible playbook for Kasten installation and configuration, run the following command:

ansible-playbook   01_k10_install.yaml

In case you are using Ansible Vaults for variables (recommended), please run the following command instead:
ansible-playbook   --ask-vault-pass 01_k10_install.yaml

## Variables
Some deployment variables must be set into the vars files.  Alter the parameters according to your needs:

[Ansible Vault](vars/vault_vars.yaml) "vault_vars.yaml" in the vars folder.
**NOTE**: It is recommended to use Ansible Vaults to keep this data instead of using just a text file, considering all the sensitive data to be kept here.


| Name                    | Type     | Default value          | Description                                                                                                            |
| ----------------------- | -------- | ---------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `company`               | `string` | `Demolab`              | Company name for EULA                                                                                                  |
| `email`                 | `string` | `pcerda@demolab.com`   | E-Mail address for EULA                                                                                                |
| `tenantID`              | `string` | `aa-431b-b-a7-1012`    | Azure Tenant ID to add Azure Blob                                                                                      |
| `azureclientID`         | `string` | `aaaaaaaaa`            | Azure Client ID to add Azure Blob                                                                                      |
| `Azureclientsecret`     | `string` | `aaaaaaaaa`            | Azure Client Secret to add Azure Blob                                                                                  |
| `azure_storage_key`     | `string` | `aaaaaaaaa`            | Azure Storage Access Key to add Azure Blob                                                                             |
| `azure_storage_env`     | `string` | `AzureCloud`           | AzureCloud is the default in Azure.  More info in https://docs.kasten.io/latest/usage/configuration.html#azure-storage |
| `bucket_name`           | `string` | `test-bucket`          | Bucket to be used as Location Profile	                                                                               |
| `bucket_region`         | `string` | `europe-west2`  		  | Bucket region                           										                                       |
| `LOGIN`                 | `string` | `admin:$apr1$aa.pY/bb/`| For K10 Basic Authentication.  Use 'htpasswd -n admin' and provide a password to autenticate to Kasten K10             |



