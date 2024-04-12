# CentOS 7 with sshd

## Usage

```shell
docker run -d \
    --name tester7 \
    --hostname tester7 \
    rea1shane/centos-sshd:7
```

or

```shell
make run HOSTNAME=tester7
```

## Build

```shell
make build
```
