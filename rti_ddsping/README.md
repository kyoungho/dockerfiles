## Locate RTI DDS Ping and its dependant libraries at your current directory
`$ cp -rf $NDDSHOME/resource/app/lib/x64Linux2.6gcc4.4.5 ./lib`
`$ cp -rf $NDDSHOME/resource/app/bin/x64Linux2.6gcc4.4.5/rtiddsping .`

## Build a Docker image
`$ docker build -t kyoungho/rti-ddsping`

## Run a Docker container
`$ docker run -tdi -e "ARGS=-publisher -numSamples 10" rti-ddsping`
