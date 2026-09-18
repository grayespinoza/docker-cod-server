FROM docker.io/i386/alpine:3.24.2

ENV IW4X_ARGS="-dedicated +set sv_lanonly 1 +set net_port 28960 +set fs_game mods/mp_bots +exec lan-dom-mp-bots.cfg +map_rotate"

RUN \
  apk add --no-cache \
    wine && \
  adduser -D -u 1000 iw4x

USER iw4x
WORKDIR /home/iw4x/server

EXPOSE 28960/udp

CMD ["sh", "-c", "exec wine ./iw4x.exe $IW4X_ARGS"]
