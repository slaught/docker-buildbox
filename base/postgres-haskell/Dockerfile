# base-postgres-haskell

FROM slaught/docker-buildbox:base-postgres

COPY  base/ /

RUN apt-get update && apt-get install -y --no-install-recommends \
     zlib1g-dev                            \
     haskell-stack                         \
     && apt-get clean                      \
     && stack upgrade                      \
     && /usr/local/bin/stack setup 8.0.2   \
     && find / -name doc |xargs rm -rf     \
     && find / -name \*.tar.xz |xargs rm -rf  


