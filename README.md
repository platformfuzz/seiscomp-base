# seiscomp-base

![CI](https://github.com/platformfuzz/seiscomp-base/actions/workflows/ci.yml/badge.svg)
![Build and Release](https://github.com/platformfuzz/seiscomp-base/actions/workflows/build-and-release.yml/badge.svg)

Unofficial SeisComP base image built with public gsm. Not gempa-supported.

Ubuntu 24.04, gsm `seiscomp` + `world-minimal`, and the Ubuntu 24.04 base dependency installer. The GUI image layers on this.

**Package:** [ghcr.io/platformfuzz/seiscomp-base](https://github.com/platformfuzz/seiscomp-base/pkgs/container/seiscomp-base)

## Run

```bash
docker pull ghcr.io/platformfuzz/seiscomp-base:7.3.1
docker run --rm -it ghcr.io/platformfuzz/seiscomp-base:7.3.1
```

## Build

```bash
docker build -t seiscomp-base:test .
```

Tag `v*` publishes GHCR and fires `repository_dispatch` `seiscomp-base-released` on `seiscomp-gui` so the pin workflow does not wait for the daily cron. That job needs the same App secrets as GUI (`SEISCOMP_BUMP_APP_CLIENT_ID`, `SEISCOMP_BUMP_APP_PRIVATE_KEY`) on this repo. The App does not need to be installed here; it only needs access to `seiscomp-gui`.
