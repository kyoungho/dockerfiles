FROM ubuntu:18.04

# $NDDSHOME/resource/app/lib/x64Linux2.6gcc4.4.5 should be located at ./lib
# $NDDSHOME/resource/app/bin/x64Linux2.6gcc4.4.5/rtiddsspy should be located at your current directory
# To build this image:
# $ docker build -t rtiddsspy .
# Example commands for running the image:
# $ docker run -tdi rtiddsspy
# $ docker run -tdi -e "ARGS=-domainId 10 -printSample" rtiddsspy

ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/app/lib
ENV ARGS=

COPY . /app

WORKDIR /app

CMD ./rtiddsspy ${ARGS}
