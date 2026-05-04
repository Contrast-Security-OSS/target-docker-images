FROM node:lts-alpine@sha256:d1b3b4da11eefd5941e7f0b9cf17783fc99d9c6fc34884a665f40a06dbdfc94f

RUN addgroup -g 2000 travis && \
  adduser -u 2000 -G travis -s /bin/sh -D travis && \
  apk --no-cache add g++ gcc libgcc libstdc++ linux-headers make python3 git && \
  ln -sf python3 /usr/bin/python && \
  python --version

USER node
ENV HOME=/home/node

# Disable npm update check
ENV NO_UPDATE_NOTIFIER=true
ENV npm_config_update_notifier=false

WORKDIR /repo

ENTRYPOINT ["sh"]
CMD ["scripts/build-generic.sh", "alpine"]
