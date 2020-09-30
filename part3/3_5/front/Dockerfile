FROM node:12-alpine

WORKDIR "/frontend_example_docker"
COPY . .

ENV NPM_CONFIG_PREFIX=/home/node/.npm-global \ 
    PATH=$PATH:/home/node/.npm-global/bin \ 
    NODE_ENV=production

RUN npm install && \ 
    rm -rf /var/lib/apt/lists/* && \
    npm cache clean --force && \    
    chown -R node /frontend_example_docker 


USER node

EXPOSE 5000

CMD [ "npm", "start" ]
