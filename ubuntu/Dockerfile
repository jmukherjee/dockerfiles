#
# Ubuntu Dockerfile
#
# https://github.com/jmukherjee/dockerfiles/ubuntu
#

# Pull base image.
FROM ubuntu:14.04

MAINTAINER Jayant <mukherjeejayant@gmail.com>

# Update.
RUN sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list
RUN apt-get update
# RUN apt-get -y upgrade

# Install.
RUN apt-get install -y build-essential && \
  apt-get install -y software-properties-common && \
  apt-get install -y byobu curl git htop man unzip vim wget nano

# Clean up.
RUN rm -rf /var/lib/apt/lists/*

# Add files.
ADD root/.bashrc /root/.bashrc
ADD root/.gitconfig /root/.gitconfig
ADD root/.scripts /root/.scripts

# Set environment variables.
ENV HOME /root

# Define working directory.
WORKDIR /root

# Define default command.
CMD ["bash"]