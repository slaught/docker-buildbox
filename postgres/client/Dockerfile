# postgres-client

# FROM slaught/docker-buildbox:base-box
FROM 7b77a1528d9e

RUN set -ex; \
# pub   4096R/ACCC4CF8 2011-10-13 [expires: 2019-07-02]
#       Key fingerprint = B97B 0AFC AA1A 47F0 44F2  44A0 7FCC 7D46 ACCC 4CF8
# uid                  PostgreSQL Debian Repository
  key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; \
  export GNUPGHOME="$(mktemp -d)"; \
  do \
    gpg --batch --keyserver hkp://ha.pool.sks-keyservers.net --recv-keys "$key" || \
    gpg --batch --keyserver hkp://ipv4.pool.sks-keyservers.net --recv-keys "$key" || \
    gpg --batch --keyserver hkp://pgp.mit.edu:80 --recv-keys "$key" ; \
  done \
  gpg --batch --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; \
  command -v gpgconf > /dev/null && gpgconf --kill all; \
  rm -rf "$GNUPGHOME"; \
  apt-key list

RUN set -ex; \
  echo "deb http://apt.postgresql.org/pub/repos/apt/ stretch-pgdg main 11" > /etc/apt/sources.list.d/pgdg.list; \
      apt-get -q update; \
  echo "New repo"

RUN apt-get -q update && apt-get -q -y --no-install-recommends install \
    libpq-dev                 \
    postgresql-client-common  \
    postgresql-common         \
    postgresql-client-11      \ 
    postgresql-11             \
    postgresql-server-dev-11  \
    pgtap                     \
    sudo                      \
    && apt-get clean

