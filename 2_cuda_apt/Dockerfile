ARG CUDA_VERSION=9.0
ARG CUDNN_VERSION=7
FROM nvidia/cuda:${CUDA_VERSION}-cudnn${CUDNN_VERSION}-devel-ubuntu16.04

MAINTAINER gHtdoCAcHEtIn


#--------------------------------------------------#
#           Ubuntu dependencies                    #
#--------------------------------------------------#

RUN apt update && apt install -y \
        bc build-essential cmake curl g++ gfortran git \ 
        pkg-config unzip wget vim nano \
        libffi-dev libfreetype6-dev libhdf5-dev liblcms2-dev \
        libopenblas-dev liblapack-dev liblapacke-dev \
        libssl-dev \
        libwebp-dev libzmq3-dev \
        software-properties-common \
        zlib1g-dev libvtk6-dev qt5-default \
        libtiff5-dev libpng12-dev libjpeg-dev libwebp-dev libpng-dev \
        libjasper-dev \
        libopenexr-dev \
        libgdal-dev \
        libdc1394-22-dev \
        libavcodec-dev libavformat-dev libswscale-dev \
        libtheora-dev libvorbis-dev libxvidcore-dev libx264-dev \
        yasm \
        libopencore-amrnb-dev \
        libopencore-amrwb-dev \
        libv4l-dev libxine2-dev libtbb-dev libeigen3-dev \
        ant default-jdk doxygen \
        && \
# Link BLAS library to use OpenBLAS using the alternatives mechanism (https://www.scipy.org/scipylib/building/linux.html#debian-ubuntu)
    update-alternatives --set libblas.so.3 /usr/lib/openblas-base/libblas.so.3

#--------------------------------------------------#
#           Clean Up                               #
#--------------------------------------------------#

# Clean up
RUN apt clean && \
    apt autoremove && \
    rm -rf /var/lib/apt/lists/*

