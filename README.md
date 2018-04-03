# CasinoCoind Docker containers
Easy way to run a CasinoCoind node in just minutes using docker. This project contains two docker 
files for creating two types of CasinoCoin nodes. 

## Basic node
The basic node runs a plain text websocket. 

[view the README.md](basic/README.md)

## Secured node 
The secured node runs a websocket secured by your pre-generated SSL certificate. I aim 
to provide a secured containerized node to operate as a relay node when the CasinoCoin 
Foundation starts accepting relay nodes. 

[View the README.md](secured/README.md)

## Build info
Build tested on a low performing VPS (2 vCPU and 4 GB RAM)
- 2.3 GB disk usage
- 10 minutes build time