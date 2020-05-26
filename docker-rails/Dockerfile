FROM ruby:2.6.6-alpine3.11

ENV TMP="/tmp"
ENV LANG=C.UTF-8
ENV TZ=Asia/Tokyo
ENV WORKSPACE="/workspace"

WORKDIR ${TMP}

RUN apk update && \
    apk upgrade && \
    apk add --no-cache \
    gcc \
    g++ \
    libc-dev \
    libxml2-dev \
    linux-headers \
    make \
    nodejs \
    postgresql \
    postgresql-dev \
    tzdata \
    git \
    yarn && \
    apk add --virtual build-packages --no-cache \
    build-base \
    curl \
    bash \
    curl-dev

RUN touch ~/.bashrc \
&& curl -o- -L https://yarnpkg.com/install.sh | bash \
&& ln -s "$HOME/.yarn/bin/yarn" /usr/local/bin/yarn

COPY Gemfile ${TMP}
COPY Gemfile.lock ${TMP}

RUN bundle install
RUN apk del build-packages

WORKDIR ${WORKSPACE}
