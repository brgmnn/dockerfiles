FROM ruby:2.3

RUN apt-get update -qq && \
    apt-get install -y build-essential libpq-dev && \
    mkdir /app

WORKDIR /app

ADD Gemfile* /app/

RUN bundle install --with development test

ADD . /app
