---
name: "Rails用のDockerfile"
slug: "vhaualb"
tags: ["Ruby"]
---

# Rails用のDockerfile

```dockerfile
FROM ruby:2.6.6-alpine3.12 as builder
RUN apk --update add --virtual build-dependencies \
    build-base \
    curl-dev \
    mariadb-dev \
    linux-headers && \
    gem install bundler
WORKDIR /tmp
COPY Gemfile Gemfile
COPY Gemfile.lock Gemfile.lock
ENV BUNDLE_JOBS=4
RUN bundle install --without development test && \
    apk del --purge build-dependencies

FROM ruby:2.6.6-alpine3.12
RUN apk --update add \
    mariadb-dev \
    tzdata && \
    gem install bundler

WORKDIR /tmp
COPY --from=builder /usr/local/bundle /usr/local/bundle

ENV APP_HOME /app
RUN mkdir -p $APP_HOME
WORKDIR $APP_HOME
COPY . $APP_HOME

CMD ["bundle","exec","rails","s"]
```

## 解説

- マルチステージビルドで余計なファイルをイメージに含めないようにする。
