FROM ubuntu:18.04

ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/app/lib
ENV ARGS=

COPY . /app

WORKDIR /app

CMD ./rtiddsping ${ARGS}
