FROM node:12-alpine as build-stage

WORKDIR "/usr/app"
COPY . .

ENV NPM_CONFIG_PREFIX=/home/node/.npm-global \ 
    PATH=$PATH:/home/node/.npm-global/bin \ 
    NODE_ENV=production

RUN npm install && npm run build

FROM node:12-alpine

WORKDIR "/frontend_example_docker"
COPY --from=build-stage /usr/app/dist/ /frontend_example_docker/dist

RUN npm install && \
    npm install -g serve

EXPOSE 5000

CMD serve -s -l 5000 dist
