FROM ruby:2.6.0

WORKDIR /114

COPY . .

RUN apt-get update && apt-get install -y nodejs

RUN gem install bundler:1.17.2

RUN gem install nokogiri

RUN bundle install

RUN rails db:migrate

EXPOSE 3000

CMD rails s