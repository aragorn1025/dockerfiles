FROM nvidia/cuda:10.2-devel-ubuntu18.04

MAINTAINER Aragorn tzjie.dai@gmail.com

ENV NVIDIA_DRIVER_CAPABILITIES=compute,utility \
	NVIDIA_VISIBLE_DEVICES=all \
	CUDA_HOME=/usr/local/cuda \
	LD_LIBRARY_PATH=/usr/local/nvidia/lib:/usr/local/nvidia/lib64 \
	LIBRARY_PATH=/usr/local/cuda/lib64/stubs \
	PATH=/usr/local/nvidia/bin:/usr/local/cuda/bin:$PATH

RUN apt-get update
RUN apt-get install -y vim \
 && echo "set number" >> ~/.vimrc
RUN apt-get install -y git
RUN apt-get install -y openssh-server
ARG ANACONDA_VERSION_CODE="2020.07"
RUN apt-get install -y wget \
 && wget https://repo.anaconda.com/archive/Anaconda3-${ANACONDA_VERSION_CODE}-Linux-x86_64.sh -O anaconda3.sh \
 && bash anaconda3.sh -b \
 && rm anaconda3.sh \
 && /root/anaconda3/bin/conda init \
 && echo "conda deactivate" >> ~/.bashrc \
 && echo "" >> ~/.bashrc

RUN echo "cd /home/" >> ~/.bashrc
WORKDIR /home/

