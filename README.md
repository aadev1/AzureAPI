# To run the Flask API inside of a container, the Docker image must exist inside of Azure Container Registry

## To build the Docker image
docker build -t aaflask .

## To create the Azuure Container Registry

az acr create --name githubactionsaa --resource-group githubactionsacr --sku Standard

## To log into the ACR from the terminal

az acr login --name githubactionsaa

## To tag and push the Docker image and prepare it for a push to ACR

docker tag aaflask githubactionsaa.azurecr.io/aaflask/flask
docker push githubactionsaa.azurecr.io/aaflask/flask