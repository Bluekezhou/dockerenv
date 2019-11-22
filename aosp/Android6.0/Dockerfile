FROM ubuntu:14.04
MAINTAINER Bluecake <bluekezhou@outlook.com>

# set proxy
RUN echo "Acquire::http::Proxy \"http://server.com:port\";" > /etc/apt/apt.conf
ENV HTTP_PROXY 'http://server.com:port'
ENV HTTPS_PROXY 'http://server.com:port'

# install dependency
RUN apt update
RUN apt install -y git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev
RUN apt install -y gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev x11proto-core-dev
RUN apt install -y libx11-dev lib32z-dev libgl1-mesa-dev libxml2-utils xsltproc unzip python openjdk-7-jdk

# prepare the enviroment
# compile with normal privilege to avoid trouble
RUN useradd aosp
WORKDIR /home/aosp
USER aosp
