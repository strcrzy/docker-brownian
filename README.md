Brownian Dockerfile
==================

This repository contains a **Dockerfile** of [Brownian](https://github.com/grigorescu/Brownian) for [Docker](https://www.docker.io/)'s [trusted build](https://index.docker.io/u/strcrzy/brownian/) published to the public [Docker Registry](https://index.docker.io/).

### Dependencies

* [debian:jessie](https://index.docker.io/_/debian/)

### Installation

1. Install [Docker](https://www.docker.io/).

2. Download [trusted build](https://index.docker.io/u/strcrzy/brownian/) from public [Docker Registry](https://index.docker.io/): `docker pull strcrzy/brownian`

#### Alternatively, build an image from Dockerfile
```bash
$ docker build -t strcrzy/brownian github.com/strcrzy/docker-brownian
```
### Usage
1. Start an [elasticsearch](https://index.docker.io/u/dockerfile/elasticsearch/) container, and give it a name

```bash
$ docker run -d --name=elasticsearch dockerfile/elasticsearch  
```

2. Start a `brownian` container, making sure to `--link` in the elasticsearch container as `elasticsearch`

```bash
$ docker run -d -p 8080 --link elasticsearch:elasticsearch strcrzy/brownian  
```
