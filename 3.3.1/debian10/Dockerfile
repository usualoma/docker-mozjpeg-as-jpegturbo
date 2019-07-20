FROM debian:10

ENV VERSION 3.3.1

WORKDIR /root/build

ADD https://github.com/mozilla/mozjpeg/archive/v$VERSION.tar.gz /root/build/
RUN set -ex \
  \
  && tar -xvf v$VERSION.tar.gz \
  && mv mozjpeg-$VERSION mozjpeg

WORKDIR /root/build/mozjpeg

RUN set -ex \
  \
  && apt-get update -qq \
  && apt-get install -y --no-install-recommends \
    autoconf \
    automake \
    libtool \
    nasm \
    make \
    pkg-config \
    \
    devscripts \
	debhelper \
    build-essential \
  && rm -rf /var/lib/apt/lists/*
