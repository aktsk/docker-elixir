FROM monsantoco/min-jessie:latest

MAINTAINER Shinta Hatatani <shinta.hatatani@aktsk.jp>

# LC_ALL が設定されていないと Locale が latin 扱いされ警告が出るので UTF-8 に設定する
ENV LC_ALL=C.UTF-8

RUN apt-get update && \
    apt-get install -y --no-install-recommends libssl1.0.0 && \
    rm -rf /var/cache/apt/archives/* /var/lib/apt/lists/*
