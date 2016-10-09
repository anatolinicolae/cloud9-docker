Alpine Linux Cloud9 v1 Dockerfile [![](https://images.microbadger.com/badges/image/anatolinicolae/alpine-cloud9.svg)](https://microbadger.com/images/anatolinicolae/alpine-cloud9 "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/anatolinicolae/alpine-cloud9.svg)](https://microbadger.com/images/anatolinicolae/alpine-cloud9 "Get your own version badge on microbadger.com")
=============

This repository contains Dockerfile of Cloud9 IDE running on Alpine Linux for Docker's automated build published to the public Docker Hub Registry.

# Base Docker Image
[gliderlabs/docker-alpine](https://github.com/gliderlabs/docker-alpine)

# Installation

## Install Docker.

Download automated build from public Docker Hub Registry: docker pull anatolinicolae/alpine-cloud9

(alternatively, you can build an image from Dockerfile: docker build -t="anatolinicolae/alpine-cloud9" github.com/anatolinicolae/cloud9-docker)

## Usage

    docker run -it -d -p 80:80 anatolinicolae/alpine-cloud9
    
You can add a workspace as a volume directory with the argument *-v /your-path/workspace/:/workspace/* like this :

    docker run -it -d -p 80:80 -v /your-path/workspace/:/workspace/ anatolinicolae/alpine-cloud9
    
## Build and run with custom config directory

Get the latest version from github

    git clone https://github.com/anatolinicolae/alpine-cloud9
    cd cloud9-docker/

Build it

    sudo docker build --force-rm=true --tag="$USER/alpine-cloud9:latest" .
    
And run

    sudo docker run -d -p 80:80 -v /your-path/workspace/:/workspace/ $USER/alpine-cloud9:latest
    
Enjoy !!    
