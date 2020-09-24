# ----------------------------------------------------#
# ubuntu        18.04
# python        3.6
# tensorflow    2.3
# cuda          10.1
# cudnn         7.6
# ----------------------------------------------------#
ARG BASE_IMAGE_TYPE=runtime

FROM nvidia/cuda:10.1-cudnn7-${BASE_IMAGE_TYPE}-ubuntu18.04

# ----------------------------------------------------#
# Install Linux Packages
# ----------------------------------------------------#
RUN apt update -y && apt install -y \
        curl \
        vim \
        build-essential \
        pkg-config \
        unzip \
        wget \
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
# Install Python Packages
# ----------------------------------------------------#
RUN pip3 install --upgrade pip
RUN pip3 install -U setuptools
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
        tensorflow \
        tensorflow-hub  && \
    python3 -m ipykernel.kernelspec

# ----------------------------------------------------#
# Port Setting
# ----------------------------------------------------#
# TensorBoard
EXPOSE 6006
# Jupyter
EXPOSE 8888
