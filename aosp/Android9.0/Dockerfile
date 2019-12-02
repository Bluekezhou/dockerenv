FROM ubuntu:18.04
MAINTAINER Bluecake <bluekezhou@outlook.com>

# set proxy
RUN echo "Acquire::http::Proxy \"http://proxy.corp.qihoo.net:8080\";" > /etc/apt/apt.conf
ENV HTTP_PROXY 'http://proxy.corp.qihoo.net:8080'
ENV HTTPS_PROXY 'http://proxy.corp.qihoo.net:8080'

# install dependency
RUN apt update
RUN apt install -y openjdk-8-jdk

# prepare the enviroment
# compile with normal privilege to avoid trouble
RUN useradd aosp
WORKDIR /home/aosp
RUN chown aosp:aosp /home/aosp
USER aosp
