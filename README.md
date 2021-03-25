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

`-it`                                  - attach a terminal session so we can see what is going on

`-p 1880:1880`                       - connect local port 1880 to the exposed internal port 1880    

`-v myNodeREDdata:/data`  - mount the host myNodeREDdata directory to the container /data directory so any changes made to flows are persisted    

`--name mynodered`             - give this machine a friendly local name    

`nodered/node-red`               - the image to base it on - currently Node-RED v1.2.0

We get the container up and running listening on port 1880 at http://127.0.0.1:1880/ mapped to port 80 on host looks like this:

# Install a node-red docker container
To install  `node-red docker container` and customize it with the UI dashboard nodes manually we will follow those steps:

Step1. stop our container with `docker stop  mynodered` 

Step2. Restart it with`docker start mynodered`

Since it's not an interactive mode to attach to that container and interact with it, we will need additional commands to start the shell as well to interact with the system:
`docker exec -it mynodered /bin/bash`
We should check if there are some adds-in home directory with `ls` and `clear` it changing to `data` directory with `cd /data` where we want our actual installation to happen.

We also want to use the network package manager command  and install node-red-dashboard:
`npm install node-red-dashboard`
If we `exit` , `stop` and `start` this `node`with:

`exit`

`docker stop  mynodered`

`docker start mynodered`

after reloading the page we can see that there is a dashboard node added.
