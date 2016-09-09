FROM elixir:1.3-slim

MAINTAINER Shinta Hatatani <shinta.hatatani@aktsk.jp>

# debconf のエラーを抑制する
ARG DEBIAN_FRONTEND=noninteractive

# wget と curl だと wget の方が依存が少ない
RUN apt-get update && apt-get install -y wget && \
    wget https://deb.nodesource.com/setup_6.x -O - | bash - && \
    apt-get install -y --no-install-recommends gcc make nodejs rsync && \
    mix local.rebar --force && \
    mix local.hex --force && \
    rm -rf /var/cache/apt/archives/* /var/lib/apt/lists/*
