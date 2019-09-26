FROM ubuntu:18.04

ENV perftest_args=

RUN apt-get update \
  && apt-get install -y wget \
  && rm -rf /var/lib/apt/lists/*

RUN wget https://github.com/rticommunity/rtiperftest/releases/download/3.0.1/rti_perftest-3.0.1_connext_dds_pro_6.0.0_x64Linux.tar.gz && \
tar xvfz rti_perftest-3.0.1_connext_dds_pro_6.0.0_x64Linux.tar.gz

RUN mkdir /app && \
cp rti_perftest-3.0.1_x64Linux3gcc4.8.2/perftest_qos_profiles.xml /app/perftest_qos_profiles.xml && \ 
cp rti_perftest-3.0.1_x64Linux3gcc4.8.2/bin/x64Linux3gcc4.8.2/release/perftest_cpp /app/perftest_cpp

COPY perftest_async_qos_profiles.xml /app/perftest_async_qos_profiles.xml

RUN rm -rf rti_perftest-3.0.1_connext_dds_pro_6.0.0_x64Linux.tar.gz && \
rm -rf rti_perftest-3.0.1_x64Linux3gcc4.8.2

CMD ./perftest_cpp -sub ${perftest_args}

WORKDIR /app
