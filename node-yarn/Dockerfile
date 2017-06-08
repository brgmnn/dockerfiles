FROM node:latest
LABEL maintainer "Daniel Bergmann"

# Add yarn
RUN apt-get update -qq >/dev/null && \
    apt-get install -qq apt-transport-https >/dev/null && \
    curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
    echo "deb https://dl.yarnpkg.com/debian/ stable main" > /etc/apt/sources.list.d/yarn.list && \
    apt-get update -qq >/dev/null && \
    apt-get install -y yarn

# Add package files
ADD package.json yarn.lock /app/
WORKDIR /app
ENV PATH /node_modules/.bin:$PATH

# Install node modules
RUN yarn install --modules-folder /node_modules --pure-lockfile --non-interactive --silent

# Add app files
ADD . /app/

ENTRYPOINT ["node"]
