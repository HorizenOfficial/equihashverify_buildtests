FROM node:carbon-alpine

MAINTAINER cronic@zensystem.io

ARG GITHUB_USER

ARG GITHUB_PASS

RUN apk add --no-cache git python build-base libsodium-dev boost-dev \
    && npm install -g mocha

USER node

RUN cd ~ \
    && git clone https://$GITHUB_USER:$GITHUB_PASS@github.com/ZencashOfficial/equihashverify.git \
    && cd ./equihashverify \
    && npm install

WORKDIR /home/node/equihashverify

CMD ["mocha"]

