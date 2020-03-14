# Docker systemd

Image variants:
- Centos 7: `burhantog/systemd-ssh:centos`
- Ubuntu 18.04: `burhantog/systemd-ssh:ubuntu`
- Debian stretch: `burhantog/systemd-ssh:debian`

## Run Centos 7
```
docker run --privileged --name centos -v /sys/fs/cgroup:/sys/fs/cgroup:ro \
        -p 2221:22 -dt burhantog/systemd-ssh:centos
```

Login to centos via ssh using ssh key:
```
docker cp centos:/root/.ssh/root.pem centos.pem
ssh -i centos.pem -p 2221 root@localhost
```

## Run Ubuntu 18.04
```
docker run --privileged --name ubuntu -v /sys/fs/cgroup:/sys/fs/cgroup:ro \
        -p 2222:22 -dt burhantog/systemd-ssh:ubuntu
```

Login to ubuntu via ssh using ssh key:
```
docker cp ubuntu:/root/.ssh/root.pem ubuntu.pem
ssh -i ubuntu.pem -p 2222 root@localhost
```

## Run Debian Stretch
```
docker run --privileged --name debian -v /sys/fs/cgroup:/sys/fs/cgroup:ro \
        -p 2223:22 -dt burhantog/systemd-ssh:debian
```

Login to debian via ssh using ssh key:
```
docker cp debian:/root/.ssh/root.pem debian.pem
ssh -i debian.pem -p 2223 root@localhost
```
