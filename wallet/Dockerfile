FROM node:8.15.0-stretch-slim

RUN set -x \
 && apt update \
 && apt install -y --no-install-recommends \
                    sudo \
                    git \
                    curl \
                    wget \
                    nano \
                    ca-certificates \
                    bzip2 \
                    python \
                    build-essential \
 && apt clean \
 && apt autoremove

RUN git config --global url."https://".insteadOf git://

WORKDIR /home

RUN git clone https://github.com/nezirin777/vips-wallet.git

WORKDIR /home/vips-wallet


RUN npm install -g cordova@8.0.0
RUN npm install --production
RUN cordova prepare


CMD npm run dev


