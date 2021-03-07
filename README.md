# Node_red_Docker

## Node-RED
Node-RED is a flow-based programming tool, originally developed by IBM’s Emerging Technology Services team and now a part of the JS Foundation.
You can get Node-RED installed and running whether on your local computer, a device such as a Raspberry Pi, or in the cloud. We will focus on running using Docker. 

To run Node-RED in Docker in its simplest form just run:

```
docker run -it -p 1880:1880 -v myNodeREDdata:/data --name mynodered nodered/node-red

```

