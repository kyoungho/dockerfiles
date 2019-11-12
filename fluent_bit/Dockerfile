# Connext DDS package installation has be located at $CONNEXT_DDS

# Example commands for running the image:
# $ docker run -tdi -v $PWD/fluent-bit.conf:/app/fluent-bit.conf fluent-bit

FROM ubuntu:18.04 as builder

ARG CONNEXT_DDS=rti_connext_dds-6.0.0
ENV NDDSHOME=/rti_connext_dds
ENV ARCHITECTURE=x64Linux2.6gcc4.4.5

COPY $CONNEXT_DDS $NDDSHOME

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    ca-certificates \
    build-essential \
    git \
    cmake \
    make \
    wget \
    flex \
    bison \
    && cd / && git clone https://github.com/kyoungho/fluent-bit.git && \
    cd /fluent-bit/build && cmake .. && make

FROM ubuntu:18.04

ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/app/lib

COPY --from=builder /fluent-bit/build/bin/fluent-bit /app/fluent-bit
COPY --from=builder /fluent-bit/conf/out_dds.conf /app/fluent-bit.conf

RUN apt-get update && \ 
    apt-get install -y ca-certificates

WORKDIR /app
CMD ./fluent-bit -c fluent-bit.conf
