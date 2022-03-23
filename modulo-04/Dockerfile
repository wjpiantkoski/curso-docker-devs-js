FROM node:16

WORKDIR /usr/src/app

COPY workspace/crud-node-postgres/package*.json ./
RUN npm install

COPY ./workspace/crud-node-postgres/ .

RUN npm install -g bower
COPY workspace/crud-node-postgres/bower*.json ./
RUN bower install --allow-root

EXPOSE 3090

CMD [ "node", "server.js" ]