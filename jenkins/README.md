# Jenkins + terraform

## Install the following plugins:
- [Azure Credentials](https://plugins.jenkins.io/azure-credentials/)

## Create a Jenkins API Token to connect via jenkins-cli. On the Jenkins Home screen:
- Manage Jenkins -> Manage Users
- Select the user you created -> Configure
- API Token -> Add new Token -> Generate -> copy

## Get the sucription id
- resourceGroup="terraform_group"
- subId=$(az account show --output tsv --query id)

## Create a principal
- az group create --name $resourceGroup --location eastus
    - Create an azure credential with the returned data, named: "azure-credentials"

## Create storage account and a storage container
- az storage account create  --name jenkinsterraformsa  --resource-group $resourceGroup --location eastus
- az storage container create --account-name jenkinsterraformsa --name jenkinsterraformac
### Get the primary key
    - az storage account keys list -g $resourceGroup -n jenkinsterraformsa - -query [0].value -o tsv
        - Create a text credential named: "access-key"

