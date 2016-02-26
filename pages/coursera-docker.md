# Coursera Docker Image

In the course, we will use docker to ensure that we work on the same configuration of the development environment.

## Setup Docker

Docker is already setup in the HG terminal rooms.

A minimal test:

    docker run hello-world

Initiate the next steps to get the Cloudera image running; either in the terminal rooms, or at home/anywhere.

## Setup Cloudera docker image in terminal rooms

    docker import - cloudera/quickstart:latest < /vol/practica/BigData/cloudera-docker-image.tar

## Setup Cloudera docker image at home

    docker pull cloudera/quickstart:latest

## Start the Cloudera docker image

When running the image (i.e., starting a container), we will request the web interface to be exposed (port 80) so you can follow the tutorial using your local browser.

    docker run --hostname=quickstart.cloudera --privileged=true --name=CDH -t -i -p 80 docker.io/cloudera/quickstart /usr/bin/docker-quickstart

Using the `-i` option opens an interactive shell, `-t` creates a pseudo-TTY. 
You can detach the terminal with key sequence `Ctrl-p``Ctrl-q`.
**TODO:** more on attach detach

The port where the tutorial is started can be requested the combination of

    docker ps

and, using the container's hash,

    docker port HASH

You can assign a name to a container with, e.g., `--name=CDH`; then subsequent commands can use the given name instead of its hash, e.g., `docker port CDH`.

## Using Cloudera docker image

In image do:

    mysql --user=retail_dba --password=cloudera  retail_db

*Etc.*


