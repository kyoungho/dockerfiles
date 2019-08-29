FROM ubuntu:18.04

RUN apt-get update \
  && apt-get install -y wget \
  && rm -rf /var/lib/apt/lists/*

RUN wget https://s3.amazonaws.com/RTI/Bundles/6.0.0/Evaluation/rti_connext_dds_secure-6.0.0-eval-x64Linux4gcc7.3.0.tar.gz \
  && tar xvfz rti_connext_dds_secure-6.0.0-eval-x64Linux4gcc7.3.0.tar.gz

RUN chmod +x rti_connext_dds-6.0.0-eval-x64Linux4gcc7.3.0.run \
  && ./rti_connext_dds-6.0.0-eval-x64Linux4gcc7.3.0.run

WORKDIR /app
