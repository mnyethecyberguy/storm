---
# draft: true
date: 2020-07-01
authors:
  - mnye
categories:
  - Docker
  - Containers
---

# How to Remove Images and Containers in Docker

![image](../../assets/images/docker-logo.png)

Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime. Using Docker, you can quickly deploy and scale applications into the cloud (or some other environment) and know your code will run.

Inevitably, when working with Docker, you will need to build, destroy, and rebuild images and containers.  The commands below can help with cleaning up those resources you no longer need.
<!-- more -->
## Removing Images

### Removing an Image

To remove a single image by using the image ID or name, use the command `docker rmi`.

To find the image name or ID, you can use `docker images` or `docker images -a`.

Once you have the ID, you can remove the image by running `docker rmi <IMAGE_ID>`.

!!! note
    You cannot remove an image that is being used by an existing container.  You must first delete the container and then remove the image.

### Removing Multiple Images

## Removing Containers

### Removing a Container

### Removing Multiple Containers