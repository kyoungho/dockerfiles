FROM ubuntu:18.04

# $NDDSHOME/resource/app/lib/x64Linux2.6gcc4.4.5 should be located at ./lib
# $NDDSHOME/resource/app/bin/x64Linux2.6gcc4.4.5/rtiroutingservice should be located at your current directory
# Example commands for running the image:
# $ docker run -tdi -v $PWD/rti_license.dat:/app/rti_license.dat rti-routingservice
# $ docker run -tdi -v $PWD/rti_license.dat:/app/rti_license.dat -v $PWD/your_config.xml:/app/config.xml -e "CFG_NAME=your_config_name" rti-routingservice

ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/app/lib
ENV CFG_NAME=default

COPY . /app

WORKDIR /app

CMD ./rtiroutingservice -cfgFile ./config.xml -cfgName $CFG_NAME
