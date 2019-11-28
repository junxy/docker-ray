# docker-ray

> 由于官方维护的docker镜像停止了更新，创建此更新．

![GitHub release (latest by date)](https://img.shields.io/github/v/release/junxy/docker-ray)
![MicroBadger Size](https://img.shields.io/microbadger/image-size/junxy/v2ray)
![MicroBadger Layers](https://img.shields.io/microbadger/layers/junxy/v2ray)
![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/junxy/v2ray)
![Docker Automated build](https://img.shields.io/docker/cloud/automated/junxy/v2ray)

已发布至 Docker Hub：https://hub.docker.com/r/junxy/v2ray

```bash
docker pull junxy/v2ray
```

- 参考官方 `Dockerfile` 制作，目录结构保持不变
    - `/etc/v2ray/config.json`: 配置文件
    - `/usr/bin/v2ray/v2ray`: V2Ray 主程序
    - `/usr/bin/v2ray/v2ctl`: V2Ray 辅助工具
    - `/usr/bin/v2ray/geoip.dat`: IP 数据文件
    - `/usr/bin/v2ray/geosite.dat`: 域名数据文件
- 经适当优化，镜像(压缩)大小仅 15M 
