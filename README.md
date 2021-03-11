# Getting started with Node-red and Docker
## Node-RED
Node-RED is a flow-based programming tool, originally developed by IBM’s Emerging Technology Services team and now a part of the JS Foundation.
You can get Node-RED installed and running whether on your local computer, a device such as a Raspberry Pi, or in the cloud. We will focus on running using Docker. 

To run Node-RED in Docker in its simplest form just run:

```
docker run -it -p 1880:1880 -v myNodeREDdata:/data --name mynodered nodered/node-red

```

This is the command breakdown:

`docker run `                          - run this container,

`-it`                                         - attach a terminal session so we can see what is going on

`-p 1880:1880`                       - connect local port 1880 to the exposed internal port 1880    

`-v myNodeREDdata:/data`  - mount the host myNodeREDdata directory to the container /data directory so any changes made to flows are persisted    

`--name mynodered`             - give this machine a friendly local name    

`nodered/node-red`               - the image to base it on - currently Node-RED v1.2.0

We get the container up and running listening on port 1880 at http://127.0.0.1:1880/ mapped to port 80 on host looks like this:


