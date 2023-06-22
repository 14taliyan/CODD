


creating AKS cluster  by using service principle.kubeconfig and service principle will be generated after the terraform plan and secret will be upload to keyvault to be used further.

## resources will be created using this terraform configuration:-
- Resource Group
- Service Principle
- AKS cluster using the SPN
- Azure key vault to store the client secret
- Secret uploaded to key vault
- kubeconfig for AKS


## Pre-requisites

- kubectl cli installed
- Azure CLI installed and logged in
- Storage Account and blob container created to store the tfstate file as backend, you  use below shell script as well

``` shell
#!/bin/bash

RESOURCE_GROUP_NAME=backend-rg
STORAGE_ACCOUNT_NAME=backendsa101
CONTAINER_NAME=tfstate

# Create resource group
az group create --name $RESOURCE_GROUP_NAME --location japanwest

# Create storage account
az storage account create --resource-group $RESOURCE_GROUP_NAME --name $STORAGE_ACCOUNT_NAME --sku Standard_LRS --encryption-services blob

# Create blob container
az storage container create --name $CONTAINER_NAME --account-name $STORAGE_ACCOUNT_NAME
```








