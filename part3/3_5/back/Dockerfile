FROM node:12-alpine

WORKDIR /backend-example-docker-master
COPY . .

ENV NODE_ENV=production \ 
    NPM_CONFIG_PREFIX=/home/node/.npm-global \ 
    PATH=$PATH:/home/node/.npm-global/bin

RUN npm install && \ 
    rm -rf /var/lib/apt/lists/*

USER node

EXPOSE 8000

CMD [ "npm", "start" ]
