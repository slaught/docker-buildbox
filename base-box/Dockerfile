# base-box

FROM debian:stretch

RUN apt-get update && apt-get install -y --no-install-recommends \
    git             \
    ssh             \
    tar             \
    gzip            \
    ca-certificates \
    build-essential \
    autoconf        \
    automake        \
    bzip2           \
    file            \
    libtool         \
    make            \
    patch           \
    xz-utils        \
    procps          \
    curl            \
    wget            \
    sudo            \
    gpg             \
    dirmngr         \
  && apt-get clean  \
  && update-ca-certificates

