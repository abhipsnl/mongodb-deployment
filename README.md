# mongodb-deployment
1. docker build -t hello-mongo:latest

FROM: Base image from which we’ll start building the container
RUN: This commands executes all instructions to install MongoDB in the base image.
ARG: Stores some default values for the Docker build. These values are not available to the container. Can be overridden during the building process of the image using the --build-arg argument.
ENV: These values are available during the build phase as well as after launching the container. Can be overridden by passing the -e argument to docker run command.
VOLUME: Attaches the data/db volume to container.
WORKDIR: Sets the work directory to execute any RUN or CMD commands.
EXPOSE: Exposes the container’s port to host the system (outside world).
CMD: Starts the mongod instance in the container

2) docker run --name my-mongo -d -v /tmp/

--name: Name of the container.
-d: Will start the container as a background (daemon) process. Don’t specify this argument to run the container as foreground process.
-v: Attach the /tmp/mongodb volume of the host system to /data/db volume of the container.
-p: Map the host port to the container port.
Last argument is the name/id of the image.
