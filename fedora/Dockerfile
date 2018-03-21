FROM fedora:latest

MAINTAINER cronic@zensystem.io

ARG GITHUB_USER

ARG GITHUB_PASS

RUN curl --silent --location https://rpm.nodesource.com/setup_8.x | bash - \
    && yum install -y libsodium-devel boost-devel nodejs gcc-c++ make git \
    && yum clean all -y \
    && rm -rf /var/cache/yum \
    && groupadd --gid 1000 node \
    && useradd --uid 1000 --gid node --shell /bin/bash --create-home -b /home node \
    && npm install -g mocha

USER node

RUN cd ~ \
    && git clone https://$GITHUB_USER:$GITHUB_PASS@github.com/ZencashOfficial/equihashverify.git \
    && cd ./equihashverify \
    && npm install

WORKDIR /home/node/equihashverify

CMD ["mocha"]
