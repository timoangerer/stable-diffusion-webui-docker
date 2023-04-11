### Build docker image



### Run as docker container

```bash 
docker run --rm -p 7860:7860 -v <absolute/path>:/data -v <absolute/path>:/output -e "CLI_ARGS=--allow-code --xformers --enable-insecure-extension-access --api" --gpus all sd-docker
```

### Push image to registry

    aws ecr get-login-password --region eu-central-1 | docker login --username AWS --password-stdin 100732661819.dkr.ecr.eu-central-1.amazonaws.com

    docker build -t sd-server .

    docker tag sd-server:latest 100732661819.dkr.ecr.eu-central-1.amazonaws.com/sd-server:latest

    docker push 100732661819.dkr.ecr.eu-central-1.amazonaws.com/sd-server:latest

    kubectl run my-shell --rm -i --tty --image 100732661819.dkr.ecr.eu-central-1.amazonaws.com/sd-server:latest -- bash