FROM ubuntu:22.04

# args
ARG TZ=Russia/Moscow
ARG DEBIAN_FRONTEND=noninteractive
ARG UID=1020
ARG LOCALE=en_US

# prapare
USER root
RUN apt update && apt install -y apt-utils

# locale setup
RUN apt install -y locales
RUN locale-gen ${LOCALE}.UTF-8
ENV LANG ${LOCALE}.UTF-8

# yocto deps part 1
RUN apt install -y gawk wget git diffstat unzip \
    texinfo gcc build-essential chrpath socat cpio python3 python3-pip \
    python3-pexpect xz-utils debianutils iputils-ping python3-git \
    python3-jinja2 libegl1-mesa libsdl1.2-dev xterm \
    python3-subunit mesa-common-dev zstd liblz4-tool

# packages for building
RUN apt install -y repo

# user setup
RUN adduser --disabled-password --gecos '' -u ${UID} dev
USER dev
WORKDIR /home/dev

# yocto deps part 2
ENV PATH="${PATH}:/home/dev/.local/bin"
RUN pip3 install pylint==2.15.5 -q