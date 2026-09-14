FROM docker.io/i386/debian:12.15-slim

ENV IW4X_ARGS="-dedicated +set sv_lanonly 1 +set net_port 28960 +set fs_game mods/mp_bots +exec lan-dom-mp-bots.cfg +map_rotate"

RUN \
  apt-get update && \
  apt-get install -y --no-install-recommends \
    wine \
    wine32 && \
  rm -rf /var/lib/apt/lists/* && \
  useradd -m -u 1000 iw4x

USER iw4x
WORKDIR /home/iw4x/server

VOLUME /home/iw4x/server
EXPOSE 28960/udp

CMD ["sh", "-c", "exec wine ./iw4x.exe $IW4X_ARGS"]
