# https://docs.docker.com/engine/reference/builder/
# https://github.com/github/pages-gem
# https://help.github.com/en/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll
FROM alpine:latest

LABEL maintainer="Mike Lee<mike@caecae.com>"

ARG GITHUB_GEM_VERSION=202

RUN apk --update add --virtual .build_deps \
    build-base \
    gcc \
    glib-dev \
    libc-dev \
    linux-headers \
    ruby-dev \
  && gem install --verbose --no-document \
    github-pages:${GITHUB_GEM_VERSION} \
  && apk del .build_deps \
  && apk add \
    git \
    ruby \
    ruby-bigdecimal \
    ruby-bundler \
    ruby-irb \
    ruby-json \
  && mkdir -p /usr/src/app \
  && rm -rf /usr/lib/ruby/gems/*/cache/*.gem

WORKDIR /usr/src/app

EXPOSE 4000 80

CMD jekyll serve -d /_site --watch --force_polling -H 0.0.0.0 -P 4000
