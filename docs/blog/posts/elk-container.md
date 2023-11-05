---
# draft: true
date: 2023-09-01
authors:
  - mnye
categories:
  - Docker
  - Containers
  - SEIM
---

# Building an ELK Stack with Docker Compose

These files can be used to create a generic ELK stack using Docker Compose.

## Prerequisites

- This assumes that you have both `git` and `docker` installed.

## Building the Containers using Docker Compose

Git clone the repository by running the following commands, one at a time:

```
git clone https://github.com/mnyethecyberguy/docker-elk.git
```
and then

```
cd docker-elk
```
Start the containers

```
docker compose up
```

## Teardown

To destroy the environment, including containers and volumes, specify the `-v` option:

```
docker compose down -v
```

## Configuration Considerations



