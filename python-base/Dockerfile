# Use an official Python runtime as a parent image
#
# usage: docker build -t python-base .

FROM debian:latest

RUN apt-get update
RUN apt-get install -y sudo ipython ipython3 python3-pip python-pip \
                       less vim && \
    apt-get clean
