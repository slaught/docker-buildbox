# base-postgres

FROM slaught/docker-buildbox:latest

RUN apt-get update && apt-get install -y --no-install-recommends \
    libpq-dev                 \
    postgresql-server-dev-9.6 \
    libpq5                    \
    postgresql-9.6            \
    postgresql-client-9.6     \ 
    postgresql-client-common  \
    postgresql-common         \
    postgresql-contrib-9.6    \
    pgtap                     \
  && apt-get clean            


