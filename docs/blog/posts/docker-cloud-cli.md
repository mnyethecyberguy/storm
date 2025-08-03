---
# draft: true
date: 2023-09-12
authors:
  - mnye
categories:
  - Docker
  - Containers
  - AWS
  - Azure
  - GCP
---

# Build a Docker Container for Cloud CLI Tools

My Docker container for Cloud CLI Tools.

This Dockerfile builds on a Ubuntu image and installs CLI tools for interacting with AWS, Azure, and GCP:

- `awscliv2` - AWS CLIv2
- `azure-cli` - Microsoft Azure CLI
- `gcloud` - Google Cloud SDK

The image also creates and runs under a non-root user.

<!-- more -->
## Using the Image

You can build the image yourself using this Dockerfile or pull from [Docker Hub](https://hub.docker.com/r/mnyethecyberguy/cloud-cli)

``` console
docker pull mnyethecyberguy/cloud-cli
```

### Building the Image Locally

Git clone the repository by running the following commands, one at a time:

``` console
git clone https://github.com/mnyethecyberguy/docker-cloud-cli.git
```
and then

``` console
cd docker-cloud-cli
```
Build the container

``` console
docker build -t cloud-cli .
```

## Dockerfile

``` dockerfile linenums="1"
FROM ubuntu

# Add a Non-Root user
RUN useradd -s /bin/bash -m ubuntu && \
    apt update && \
    apt install -y sudo && \
    echo "ubuntu ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

USER ubuntu
WORKDIR /home/ubuntu
SHELL ["/bin/bash", "-c"]
 
# AWS CLI
RUN sudo apt update && \
    sudo apt install -y curl unzip sudo && \
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && \
    sudo ./aws/install && \
    rm awscliv2.zip
 
# Azure CLI
RUN sudo apt update && \
    sudo apt install -y ca-certificates curl apt-transport-https lsb-release gnupg && \
    curl -sL https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/microsoft.gpg > /dev/null && \
    AZ_REPO=$(lsb_release -cs) && \
    echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" | sudo tee /etc/apt/sources.list.d/azure-cli.list && \
    sudo apt update && \
    sudo apt install -y azure-cli
 
# GCloud CLI
RUN echo deb [signed-by=/usr/share/keyrings/cloud.google.gpg] http://packages.cloud.google.com/apt cloud-sdk main | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list && \
    curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key --keyring /usr/share/keyrings/cloud.google.gpg  add - && \
    sudo apt update -y && \
    sudo apt install google-cloud-sdk -y
```

## Additional References

[^1]: https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html
[^2]: https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt
[^3]: https://cloud.google.com/sdk/docs/install
