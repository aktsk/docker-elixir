FROM shiguredo/erlang:shiguredo-erlang-18.3-ubuntu-16.04

MAINTAINER Shinta Hatatani <shinta.hatatani@aktsk.jp>

# elixir expects utf8.
ENV LANG=C.UTF-8

RUN set -xe \
  && ELIXIR_VERSION="v1.3.0" \
  && ELIXIR_DOWNLOAD_URL="https://github.com/elixir-lang/elixir/releases/download/${ELIXIR_VERSION}/Precompiled.zip" \
  && ELIXIR_DOWNLOAD_SHA256="cdca6cf6355ee993cf7e220cccb553c284e6c30e187251b9dae0f5e5d5207839" \
  && buildDeps=' \
    unzip \
  ' \
  && apt-get update \
  && apt-get install -y --no-install-recommends $buildDeps \
  && curl -fSL -o elixir-precompiled.zip $ELIXIR_DOWNLOAD_URL \
  && echo "$ELIXIR_DOWNLOAD_SHA256 elixir-precompiled.zip" | sha256sum -c - \
  && unzip -d /usr/local elixir-precompiled.zip \
  && rm elixir-precompiled.zip \
  && apt-get purge -y --auto-remove $buildDeps \
  && rm -rf /var/lib/apt/lists/* \
  && mix local.hex --force \
  && mix local.rebar --force
