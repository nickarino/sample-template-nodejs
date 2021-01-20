```
# from https://docs.microsoft.com/en-us/azure/container-registry/container-registry-get-started-azure-cli
# This is to create a docker container registry
# could do this in console.azure.com
#Create the resource group
az login
az group create --name nickRG --location eastus
# Create the registry in the resource group
az acr create --resource-group nickRG --name nickDockerRegistry --sku Basic
# logging into container registry via console.azure.com is a pain
# install azure cli
brew install az
#  "loginServer": "nickdockerregistry.azurecr.io",
#  "name": "nickDockerRegistry",
#get local docker
docker pull jrottenberg/ffmpeg
az acr login --name nickdockerregistry #docker must be running. 
docker tag jrottenberg/ffmpeg:latest nickdockerregistry.azurecr.io/jrottenberg/ffmpeg:v1
docker push nickdockerregistry.azurecr.io/jrottenberg/ffmpeg:v1
az acr repository list --name nickdockerregistry --output table
az acr repository show-tags --name nickdockerregistry --repository jrottenberg/ffmpeg --output table
# https://medium.com/coconut-stories/using-ffmpeg-with-docker-94523547f35c
# Shows how to use docker with code as an end result in lib
# docker run jrottenberg/ffmpeg:latest -i http://files.coconut.co.s3.amazonaws.com/test.mp4 -f webm -c:v libvpx -c:a libvorbis - > test.webm

# https://docs.microsoft.com/en-us/azure/app-service/tutorial-custom-container?pivots=container-linux
# https://docs.microsoft.com/en-us/azure/app-service/quickstart-nodejs?pivots=platform-linux
# https://microsoft.github.io/AzureTipsAndTricks/blog/tip19.html

```