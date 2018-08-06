ARG CUDA_VERSION=9.0
FROM global/cuda_py:${CUDA_VERSION}py2

MAINTAINER gHtdoCAcHEtIn

ARG OPENCV_VERSION=3.4.2

ARG PYTHON=python
ARG PYTHON_VERSION=27

#--------------------------------------------------#
#           Opencv                                 #
#--------------------------------------------------#

# Install OpenCV dependencies
RUN apt update && apt install -y \
        build-essential gcc g++ git cmake pkg-config \
        libopenblas-dev liblapacke-dev \
        ffmpeg libavcodec-dev libavformat-dev libswscale-dev libavresample-dev \
        libgtk2.0-dev gphoto2 qt5-default libdc1394-22-dev\
        ${PYTHON}-dev ${PYTHON}-tk \
        libtbb2 libtbb-dev \
        libjpeg-dev libpng-dev libtiff-dev \
        libeigen3-dev libjasper-dev

# Install OpenCV
ARG OPENCV_CONTRIB=/root/opencv/opencv_contrib-${OPENCV_VERSION}

RUN mkdir /root/opencv
# RUN cd /root/opencv && \
#   wget https://github.com/opencv/opencv/archive/${OPENCV_VERSION}.tar.gz && \
#   mv ${OPENCV_VERSION}.tar.gz opencv-${OPENCV_VERSION}.tar.gz
COPY opencv-${OPENCV_VERSION}.tar.gz /root/opencv/
COPY opencv_contrib-${OPENCV_VERSION}.tar.gz /root/opencv/

RUN cd /root/opencv && \
    tar -xzf opencv-${OPENCV_VERSION}.tar.gz && \
    tar -xzf opencv_contrib-${OPENCV_VERSION}.tar.gz && \
    cd opencv-${OPENCV_VERSION} && mkdir build && cd build && \
    cmake \
#        -DWITH_CUDA=ON -DWITH_NVCUVID=ON \
#        -DCUDA_NVCC_FLAGS="-Wno-deprecated-gpu-targets" \
        -DWITH_QT=ON -DWITH_OPENGL=ON -DFORCE_VTK=ON \
        -DWITH_TBB=ON -DWITH_OPENMP=ON -DWITH_IPP=ON \
        -DPYTHON_EXECUTABLE="/usr/bin/${PYTHON}" \
        -DBUILD_EXAMPLES=OFF -DBUILD_PERF_TESTS=OFF -DBUILD_DOCS=OFF -DBUILD_TESTS=OFF \
        -DOPENCV_EXTRA_MODULES_PATH=${OPENCV_CONTRIB}/modules \
        .. && \
    make -j"$(nproc)" && \
    make install && \
    ldconfig && \
    echo 'ln /dev/null /dev/raw1394' >> ~/.bashrc

#--------------------------------------------------#
#           Clean Up                               #
#--------------------------------------------------#

# Clean up
RUN apt clean && \
    apt autoremove && \
    rm -rf /var/lib/apt/lists/*

WORKDIR "/root"
