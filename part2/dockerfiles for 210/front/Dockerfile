FROM ubuntu:16.04

WORKDIR "/frontend_example_docker"

COPY . .

RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
RUN node -v && npm -v
RUN npm install

EXPOSE 5000

CMD [ "npm", "start" ]
