# Docker CentOS with sshd

[![docker-image-ci-7](https://github.com/rea1shane/docker-centos-sshd/actions/workflows/docker-image-ci-7.yml/badge.svg)](https://github.com/rea1shane/docker-centos-sshd/actions/workflows/docker-image-ci-7.yml)
[![docker-image-ci-8](https://github.com/rea1shane/docker-centos-sshd/actions/workflows/docker-image-ci-8.yml/badge.svg)](https://github.com/rea1shane/docker-centos-sshd/actions/workflows/docker-image-ci-8.yml)

No frills, simple Docker CentOS with sshd.

The default password for root is `1`.

## Usage

Run CentOS 7 based image:

```shell
docker run -d \
    --name centos7 \
    --hostname centos7 \
    rea1shane/centos-sshd:7
```

Run CentOS 8 based image:

```shell
docker run -d \
    --name centos8 \
    --hostname centos8 \
    rea1shane/centos-sshd:8
```

See more info:

- [CentOS 7 based image](https://github.com/rea1shane/docker-centos-sshd/tree/main/7)
- [CentOS 8 based image](https://github.com/rea1shane/docker-centos-sshd/tree/main/8)
