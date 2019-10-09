# https://docs.docker.com/engine/reference/builder/
FROM ubuntu:18.04

LABEL name="node-nvm-image"
LABEL version="0.1.0"

ARG NVM_SRC=https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.0/install.sh
ARG NODE_VERSION=6.11.1
ARG NVM_DIR=/usr/local/bin/nvm

RUN apt-get update && \
    apt-get install -yq \
        curl && \
    apt-get clean && \
    useradd -ms /bin/bash nvm && \
    mkdir -p ${NVM_DIR} && \
    chmod 777 ${NVM_DIR}

# install the NVM as user tool    
USER nvm
RUN curl -o- ${NVM_SRC} | bash

# default a SHELL to allow NVM interaction
CMD [ "bash" ]
