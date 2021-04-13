# Docker Image for ASK CLI

Original author: https://github.com/martindsouza/docker-amazon-ask-cli

## Dockerhub

https://hub.docker.com/repository/docker/duyetdev/ask-cli

## Usage

```bash
# Create a ASK configuration folders.
cd ~
mkdir alexa-demo \
  alexa-demo/ask-config \
  alexa-demo/aws-config \
  alexa-demo/app

# Note copy the aws-config information (see below) to the aws-config folder

# To help simply writing out a full docker run command each time will use an alias
alias alexa="docker run -it --rm \
  -v ~/alexa-demo/ask-config:/home/node/.ask \
  -v ~/alexa-demo/aws-config:/home/node/.aws \
  -v ~/alexa-demo/app:/home/node/app \
  duyetdev/ask-cli:latest "

# Configure ASK
alexa ask init --no-browser

# Deploy (all): this will create both lambda and Alexa Skill
alexa ask deploy

```

## Development

```bash
docker build -t duyetdev/ask-cli:latest .
docker push duyetdev/ask-cli:latest
```
