FROM node:carbon

MAINTAINER cronic@zensystem.io

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get -y --no-install-recommends install apt-utils \
    && DEBIAN_FRONTEND=noninteractive apt-get -y --no-install-recommends install git libboost-system-dev build-essential libsodium-dev \
    && npm install -g mocha

USER node

RUN cd ~ \
    && git clone https://github.com/ZencashOfficial/equihashverify.git \
    && cd ./equihashverify \
    && npm install

WORKDIR /home/node/equihashverify

CMD ["mocha"]
