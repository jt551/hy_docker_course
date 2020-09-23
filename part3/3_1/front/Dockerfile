FROM ubuntu:16.04

WORKDIR "/frontend_example_docker"

COPY . .

RUN apt-get update && apt-get install -y curl && \ 
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \ 
    apt install -y nodejs && \ 
    node -v && npm -v && \ 
    npm install && \
    apt-get purge -y --auto-remove curl && \ 
    rm -rf /var/lib/apt/lists/* && \
    npm cache clean --force

EXPOSE 5000

CMD [ "npm", "start" ]
