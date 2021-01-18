```
# from https://docs.microsoft.com/en-us/azure/container-registry/container-registry-get-started-azure-cli

# could do this in console.azure.com
az group create --name nickResourceGroup --location eastus
az acr create --resource-group nickResourceGroup --name nickDockerContainerRegistry --sku Basic
# logging into container registry via console.azure.com is a pain
# install azure cli
brew install az
az acr login --name nickDockerContainerRegistry #docker must be running. 

Nicks-MacBook-Pro:~ nick$ az acr login -n nickdockercontainerregistry -u nick_skriloff -p IloveJen1234!
Error response from daemon: Get https://nickdockercontainerregistry.azurecr.io/v2/: unauthorized: Application not registered with AAD.

# docker login directly
# https://stackoverflow.com/questions/57894603/azure-container-registry-docker-login-does-not-work
```