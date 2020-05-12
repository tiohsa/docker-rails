FROM ruby:2.6.6-alpine3.11

ENV TMP="/tmp"
ENV LANG=C.UTF-8
ENV TZ=Asia/Tokyo

WORKDIR ${TMP}

RUN apk update && \
    apk upgrade && \
    apk add --no-cache \
    libc-dev \
    libxml2-dev \
    linux-headers \
    bash \
    build-base \
    libxslt-dev

COPY Gemfile ${TMP}
RUN bundle install

ENTRYPOINT ["solargraph"]
CMD  ["socket", "--host", "0.0.0.0", "--port", "7658"]
