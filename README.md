Alpine Linux Cloud9 v1 Dockerfile
=============

This repository contains Dockerfile of Cloud9 IDE running on Alpine Linux for Docker's automated build published to the public Docker Hub Registry.

# Base Docker Image
[gliderlabs/docker-alpine](https://github.com/gliderlabs/docker-alpine)

# Installation

## Install Docker.

Download automated build from public Docker Hub Registry: docker pull sqrd/cloud9-docker

(alternatively, you can build an image from Dockerfile: docker build -t="sqrd/cloud9-docker" github.com/anatolinicolae/cloud9-docker)

## Usage

    docker run -it -d -p 80:80 sqrd/cloud9-docker
    
You can add a workspace as a volume directory with the argument *-v /your-path/workspace/:/workspace/* like this :

    docker run -it -d -p 80:80 -v /your-path/workspace/:/workspace/ sqrd/cloud9-docker
    
## Build and run with custom config directory

Get the latest version from github

    git clone https://github.com/anatolinicolae/cloud9-docker
    cd cloud9-docker/

Build it

    sudo docker build --force-rm=true --tag="$USER/cloud9-docker:latest" .
    
And run

    sudo docker run -d -p 80:80 -v /your-path/workspace/:/workspace/ $USER/cloud9-docker:latest
    
Enjoy !!    
