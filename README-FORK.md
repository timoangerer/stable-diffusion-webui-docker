### Build docker image



### Run as docker container

```bash 
docker run --rm -p 7860:7860 -v <absolute/path>:/data -v <absolute/path>:/output -e "CLI_ARGS=--allow-code --xformers --enable-insecure-extension-access --api" --gpus all sd-docker
```