# base-image for node on any machine using a template variable,
# see more about dockerfile templates here:http://docs.resin.io/pages/deployment/docker-templates
# Note the node:slim image doesn't have node-gyp
FROM resin/qemux86-64-node:6.9

# Defines our working directory in container
RUN mkdir -p /usr/src/app/
WORKDIR /usr/src/app

# This install npm dependencies on the resin.io build server,
# making sure to clean up the artifacts it creates in order to reduce the image size.
RUN JOBS=MAX npm install -g node-red node-red-contrib-resinio && npm cache clean && rm -rf /tmp/*

# This will copy all files in our root to the working  directory in the container
COPY ./app ./

# Enable systemd init system in container
# ENV INITSYSTEM=on

EXPOSE 80

# server.js will run when container starts up on the device
CMD ["bash", "/usr/src/app/start.sh"]
