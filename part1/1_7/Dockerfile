FROM ubuntu:16.04

WORKDIR /1_7

COPY scriptfile .

RUN chmod +x scriptfile

RUN apt-get update && apt-get install -y curl

CMD ["./scriptfile"] 

