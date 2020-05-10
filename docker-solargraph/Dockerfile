FROM ruby:2.7.1-alpine3.11

ENV ROOT="/tmp"
ENV LANG=C.UTF-8
ENV TZ=Asia/Tokyo

WORKDIR ${ROOT}

RUN apk update && \
    apk upgrade && \
    apk add --no-cache \
        libc-dev \
        libxml2-dev \
        linux-headers \
        bash \
        build-base \
        libxslt-dev

COPY Gemfile ${ROOT}
RUN bundle install

ENTRYPOINT ["solargraph"]
CMD  ["socket", "--host", "0.0.0.0", "--port", "7658"]
