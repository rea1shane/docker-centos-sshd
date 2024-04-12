# CentOS 8 with sshd

The default password for root is `1`.

## Usage

```shell
docker run -d \
    --name tester8 \
    --hostname tester8 \
    rea1shane/centos-sshd:8
```

or

```shell
make run HOSTNAME=tester8
```

## Build

```shell
make build
```
