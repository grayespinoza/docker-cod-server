FROM docker.io/i386/debian:12.15-slim

ENV COD4X_ARGS="+set dedicated 1 +set sv_punkbuster 0 +set sv_maxclients 16 +map_rotate +set fs_game mods/mp_bots +exec server.cfg"

RUN \
  apt-get update && \
  apt-get install -y --no-install-recommends \
    libstdc++6 \
    libgcc-s1 && \
  rm -rf /var/lib/apt/lists/* && \
  useradd -m -u 1000 cod4x

USER cod4x
WORKDIR /home/cod4x/server

VOLUME /home/cod4x/server
EXPOSE 28960/tcp 28960/udp

CMD ["sh", "-c", "exec ./cod4x18_dedrun $COD4X_ARGS"]
