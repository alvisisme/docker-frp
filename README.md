# frp docker 镜像

![https://travis-ci.com/alvisisme/docker-frp](https://img.shields.io/travis/com/alvisisme/docker-frp)
![https://cloud.docker.com/repository/docker/alvisisme/frp](https://img.shields.io/docker/pulls/alvisisme/frp.svg)

## 拉取镜像

```bash
docker pull registry.cn-hangzhou.aliyuncs.com/alvisisme/frp:frps-0.31.2
docker pull registry.cn-hangzhou.aliyuncs.com/alvisisme/frp:frpc-0.31.2
```

## 如何使用

以服务端举例

导出默认配置文件到当前目录

```bash
docker run -it registry.cn-hangzhou.aliyuncs.com/alvisisme/frp:frps-0.31.2 cat /etc/frps.ini > frps.ini
```

查看frp服务端完整配置样例

```bash
docker run -it registry.cn-hangzhou.aliyuncs.com/alvisisme/frp:frps-0.31.2 cat /etc/frps_full.ini
```

根据需求配置 **frps.ini** 后启动frp服务端

```bash
docker run -it --network host -v $PWD/frps.ini:/etc/frps.ini registry.cn-hangzhou.aliyuncs.com/alvisisme/frp:frps-0.31.2
```

或者使用docker-compose启动

```bash
docker-compose -f docker-compose-frps.yml up -d
```

客户端配置过程类似。
