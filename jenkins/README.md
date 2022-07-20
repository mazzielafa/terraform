# Jenkins + terraform

## Install the following plugins:
- [AnsiColor](https://plugins.jenkins.io/ansicolor/)
- [Azure Credentials](https://plugins.jenkins.io/azure-credentials/)
- [Azure KeyVault](https://plugins.jenkins.io/azure-keyvault/)
	- Once all plugins are installed, restart Jenkins by navigating to the url: <aci_FQDN>:8080/restart

## Run azure_admin.sh
- The azure_admin.sh script located in the scripts directory is used to create a Service Principal, Azure Storage Account and KeyVault. The Service Principal will be granted read access to the KeyVault secrets and will be used by Jenkins. The script will also set KeyVault secrets that will be used by Jenkins & Terraform.
- chmod +x ./scripts/azure_admin.sh -h && ./scripts/azure_admin.sh -h

## Run jenkins_admin.sh
- used by a Jenkins Admin to connect to the KeyVault created in the azure_admin.sh script, fetch Azure Service Principal information and store this information in Jenkins using jenkins-cli. The Azure Service Principal credentials can then be used by Jenkins to connect to Azure.
- chmod +x ./scripts/jenkins_admin.sh -h &&
    ./scripts/jenkins_admin.sh -h
    - Once you have run the script:
    	- Log into Jenkins
    	- Manage Jenkins -> Manage Credentials and you should see the credentials the script loaded into Jenkins

## Create and Run Jenkins Job
- See Jenkinsfile-terraform

## Run cleanup_azure.sh
- The cleanup_azure.sh script located in the scripts directory is used to delete Azure resources created by the scripts during the tutorial.
- chmod +x ./scripts/cleanup_azure.sh -h && ./scripts/cleanup_azure.sh -h