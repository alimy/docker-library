# Version: 0.1
FROM node:12.9.0-stretch
MAINTAINER Michael Li "alimy@gility.net"
RUN apt-get update && apt-get install -y \
  bison \
  build-essential \
  curl \
  g++-multilib \
  gcc-multilib \
  git \
  gperf \
  libgnome-keyring-dev \
  libnotify-dev \
  libssl-dev \
  lsb-release \
  ninja-build \
  python-pip \
  sudo

RUN alias ls='ls --color' && alias ll='ls -l'

RUN npm install -g node-gyp@5.0.3
RUN pip install Jinja2

RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
ENV PATH="/root/.cargo/bin:${PATH}"
RUN cargo install sccache
RUN echo "sccache = /root/.cargo/bin/sccache" > /root/.npmrc

WORKDIR /root
VOLUME /root/art/arm/brave

VOLUME /root/.cache/sccache

CMD bash
