FROM ubuntu:18.04

ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/app/lib
ENV CFG_NAME=default
ENV ARGS=

COPY . /app

WORKDIR /app

CMD ./rtiroutingservice -cfgFile ./config.xml -cfgName $CFG_NAME $ARGS
