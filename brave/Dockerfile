# Version: 0.2
FROM ubuntu:19.10
MAINTAINER Michael Li "alimy@gility.net"
RUN apt -y update && apt -y upgrade && apt install -y \
  curl \
  git \
  vim \
  python-pip

RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash && . /root/.bashrc && nvm install v12.9.0

WORKDIR /root
VOLUME /root/art/arm/brave
VOLUME /root/.cache/sccache

CMD bash
