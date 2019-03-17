# ----------------------------------------------------#
# ubuntu    16.04
# python    3.6
# ----------------------------------------------------#
ARG BASE_IMAGE_TYPE=devel
FROM nvidia/cuda:9.0-cudnn7-${BASE_IMAGE_TYPE}-ubuntu16.04

# ----------------------------------------------------#
# Linux Packages
# ----------------------------------------------------#
RUN apt update -y && \
    apt install -y software-properties-common && \
    add-apt-repository ppa:deadsnakes/ppa
RUN apt update -y && apt install -y \
        curl \
        vim \
        build-essential \
        pkg-config \
        unzip \
        git \
        zip \
        less \
        python3.6 \
        python3.6-dev \
        python3-pip && \
    apt clean && \
    rm -rf /var/lib/apt/lists/*

# Update symbolic link to use python3.6
RUN rm /usr/bin/python3
RUN ln -s /usr/bin/python3.6 /usr/bin/python3

# ----------------------------------------------------#
# Install Python Packages under the USER environment
# ----------------------------------------------------#
ARG TENSORFLOW_VERSION=1.13.1

RUN pip3 --no-cache-dir install \
        Pillow \
        h5py \
        jupyter notebook \
        jupyterlab \
        matplotlib \
        numpy \
        pandas \
        scipy \
        scikit-learn \
        scikit-image \
        opencv-python \
        tqdm \
        tensorflow-gpu==${TENSORFLOW_VERSION} \
        tensorflow-hub  && \
    python3 -m ipykernel.kernelspec

# ----------------------------------------------------#
# Port Setting
# ----------------------------------------------------#
# TensorBoard
EXPOSE 6006
# IPython
EXPOSE 8888

