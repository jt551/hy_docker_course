FROM ubuntu:16.04

WORKDIR /backend-example-docker-master
COPY . .

RUN apt-get update && apt-get install -y curl && \ 
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \ 
    apt install -y nodejs && \ 
    npm install && \ 
    apt-get purge -y --auto-remove curl && \ 
    rm -rf /var/lib/apt/lists/* && \
    useradd -m app

USER app

EXPOSE 8000

CMD [ "npm", "start" ]
