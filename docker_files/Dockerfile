FROM ubuntu:20.04

ENV PATH="/root/miniconda3/bin:${PATH}"
ARG PATH="/root/miniconda3/bin:${PATH}"

RUN apt update && apt install wget -y

# https://github.com/conda/conda/issues/10431#issuecomment-1363739346
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh \
    && mkdir root/.conda \
    && bash Miniconda3-latest-Linux-x86_64.sh -b \ 
    && rm -f Miniconda3-latest-Linux-x86_64.sh

COPY . /breaking_bad

WORKDIR breaking_bad/

RUN conda env create -f breaking_bad.yml
