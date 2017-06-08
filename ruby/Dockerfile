FROM ruby:latest
LABEL maintainer "Daniel Bergmann"

WORKDIR /app

# Install gems
ADD Gemfile* /app/
RUN bundle install

ADD . /app/
