#####################################################################
# Ubuntu users:
# You MUST do one of the following to prevent pip3 from failing.

#####################################################################
# OPTION ONE
# Use the '--network=host' argument when building the image
#
# Example:
# * sudo may be optional *
# sudo docker build --network=host -t nirvash/mumbo .

#####################################################################
# OPTION TWO
#
# 1) 
# * with sudo privileges *
# Edit the file '/etc/default/docker' and add the following line:
#
# DOCKER_OPTS="--dns 8.8.8.8" 
#
# 2) 
# Then, restart the Docker daemon:
# sudo systemctl restart docker
#
# 3) 
# Build your docker image

#####################################################################
FROM python:3.8-buster

LABEL Maintainer="Nirvash: github@Type-Zero-Nirvash"

WORKDIR home

COPY requirements.txt /home/

RUN pip3 install -r requirements.txt
RUN apt update
RUN apt install ffmpeg libsm6 libxext6 -y
#####################################################################

#####################################################################
# To run any example, we will use a volume. 
# (Run each example from the directory you have your checkout in)
#
#####################################################################
# To see list of options available for our GNN explainer:
# Linux:
# sudo docker run --rm -v /
#    $PWD/:/home nirvash/gnn python3 /home/train.py --help
#
# Windows:
# docker run --rm -v ^ 
#    %cd%/:/home nirvash/gnn python3 /home/train.py --help
#
#####################################################################
# To train a GNN model: 
# Linux:
# sudo docker run --rm -v \
#    $PWD/:/home nirvash/gnn python3 /home/train.py \
#    --dataset=EXPERIMENT_NAME
#
# Windows:
# docker run --rm -v ^ 
#    %cd%/:/home nirvash/gnn python3 /home/train.py ^
#    --dataset=EXPERIMENT_NAME
#
#####################################################################
# To run the explainer:
# Linux:
# sudo docker run --rm -v \
#    $PWD/:/home nirvash/gnn python3 /home/explainer_main.py \
#    --dataset=EXPERIMENT_NAME
#
# Windows:
# docker run --rm -v 
#    %cd%/:/home nirvash/gnn python3 /home/explainer_main.py ^
#    --dataset=EXPERIMENT_NAME
#
#####################################################################
