FROM ubuntu:16.04

WORKDIR /backend-example-docker-master

COPY . .

RUN apt-get update && apt-get install -y curl

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs

RUN npm install

ENV FRONT_URL=http://localhost:5000

EXPOSE 8000

ENTRYPOINT [ "npm" ]
