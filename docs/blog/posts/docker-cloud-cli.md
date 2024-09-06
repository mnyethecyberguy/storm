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

``` docker
docker pull mnyethecyberguy/cloud-cli
```

### Building the Image Locally

Git clone the repository by running the following commands, one at a time:

``` bash
git clone https://github.com/mnyethecyberguy/docker-cloud-cli.git
```
and then

``` bash
cd docker-cloud-cli
```
Build the container

``` docker
docker build -t cloud-cli .
```

# Additional References

https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html
https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt
https://cloud.google.com/sdk/docs/install
