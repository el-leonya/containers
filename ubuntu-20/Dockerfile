FROM ubuntu:20.04

ARG TZ=Russia/Moscow
ARG DEBIAN_FRONTEND=noninteractive

USER root

RUN apt-get update && \ 
    apt-get install -y gawk wget git diffstat unzip \
    texinfo gcc build-essential chrpath socat cpio python3 python3-pip \
    python3-pexpect xz-utils debianutils iputils-ping python3-git \
    python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 xterm \
    python3-subunit mesa-common-dev zstd liblz4-tool \
    repo


