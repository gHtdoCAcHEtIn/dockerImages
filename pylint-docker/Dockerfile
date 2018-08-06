FROM ubuntu:16.04

MAINTAINER gHtdoCAcHEtIn

# Install some dependencies
RUN apt update && apt install -y \
        build-essential \
        git \
        nano \
        vim \
        wget \
        curl \
        python \
        python-dev \
        python3 \
        python3-dev \
        pylint \
        && \
    apt-get clean && \
    apt-get autoremove && \
    rm -rf /var/lib/apt/lists/*

WORKDIR "/root"
CMD ["/bin/bash"]
