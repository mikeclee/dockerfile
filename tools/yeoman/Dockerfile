# https://docs.docker.com/engine/reference/builder/
FROM node:12.11

LABEL name="yeoman-image"
LABEL version="0.1.0"

RUN npm install -g \
        generator-base-polymer \
        generator-generator \
        generator-react-webpack \
        yo

# default user & workdir
WORKDIR /wip

# default a SHELL to allow NVM interaction
ENTRYPOINT [ "yo" ]
CMD [ "--version" ]
