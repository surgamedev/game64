# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.245.2/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version (use ubuntu-22.04 or ubuntu-18.04 on local arm64/Apple Silicon): ubuntu-22.04, ubuntu-20.04, ubuntu-18.04
ARG VARIANT="focal"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

ARG INSTALL_ZSH="true"
ARG UPGRADE_PACKAGES="true"
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

ENV PATH=/etc/n64/usr/sbin:${PATH}
ENV PATH=/opt/crashsdk/bin:${PATH}
ENV ROOT=/etc/n64
ENV N64_LIBGCCDIR=/opt/crashsdk/lib/gcc/mips64-elf/12.2.0

RUN dpkg --add-architecture i386 && \
    apt-get update && \
    apt-get -y install build-essential git wget flex bison && \
    apt-get clean && \
    echo "deb [trusted=yes] https://crashoveride95.github.io/apt ./" > /etc/apt/sources.list.d/crashoveride95.list && \
    apt update && \
    apt-get -y install lib32z1 && \
    apt-get -y install libc6:i386 && \
    apt-get -y install binutils-mips-n64 gcc-mips-n64 newlib-mips-n64 && \
    apt-get -y install n64sdk && \
    apt-get -y install makemask && \
    apt-get -y install libnustd && \
    apt-get -y install libnusys && \
    apt-get -y install libnaudio && \
    apt-get -y install libmus && \
    apt-get -y install u64assets && \
    apt-get -y install n64graphics && \
    apt-get -y install vadpcm-tools && \
    apt-get -y install n64-conv-tools && \
    apt-get -y install rsp-tools && \
    apt-get -y install spicy && \
    apt-get -y install root-compatibility-environment