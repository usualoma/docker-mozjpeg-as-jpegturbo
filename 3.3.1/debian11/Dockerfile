FROM debian:11

ENV VERSION 4.0.3

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
    build-essential \
    nasm \
    cmake \
    ninja-build \
    curl \
    libpng-dev \
    libpng-tools \
    zlib1g-dev \
    \
    devscripts \
	debhelper \
    build-essential \
  && rm -rf /var/lib/apt/lists/*
