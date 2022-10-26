FROM ubuntu:22.04

# args
ARG TZ=Russia/Moscow
ARG DEBIAN_FRONTEND=noninteractive
ARG UID=1020

# prapare
USER root
RUN apt-get update && apt-get install -y apt-utils

# yocto deps part 1
RUN apt-get install -y gawk wget git diffstat unzip \
    texinfo gcc build-essential chrpath socat cpio python3 python3-pip \
    python3-pexpect xz-utils debianutils iputils-ping python3-git \
    python3-jinja2 libegl1-mesa libsdl1.2-dev xterm \
    python3-subunit mesa-common-dev zstd liblz4-tool

# packages for building
RUN apt-get install -y repo

# setup user
RUN adduser --disabled-password --gecos '' -u ${UID} dev
USER dev
WORKDIR /home/dev

# yocto deps part 2
ENV PATH="${PATH}:/home/dev/.local/bin"
RUN pip3 install pylint==2.15.5 -q
