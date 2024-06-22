version: '3'

services:
  metacubexd:
    container_name: metacubexd
    image: ghcr.io/metacubex/metacubexd
    restart: always
    ports:
      - '80:80'

  # optional
  meta:
    container_name: meta
    image: docker.io/metacubex/mihomo:Alpha
    restart: always
    pid: host
    ipc: host
    network_mode: host
    cap_add:
      - ALL
    volumes:
      - ./config.yaml:/root/.config/mihomo
      - /dev/net/tun:/dev/net/tun
