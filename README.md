# docker-ray

> 由于[官方维护](https://hub.docker.com/r/v2ray/official)的 docker 镜像**长时间未更新了**，创建此更新．

![GitHub tag (latest SemVer pre-release)](https://img.shields.io/github/v/tag/junxy/docker-ray?label=version)
![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/junxy/v2ray)
![Docker Automated build](https://img.shields.io/docker/cloud/automated/junxy/v2ray)

![MicroBadger Layers](https://img.shields.io/microbadger/layers/junxy/v2ray)
![MicroBadger Size](https://img.shields.io/microbadger/image-size/junxy/v2ray)

已发布至 Docker Hub：https://hub.docker.com/r/junxy/v2ray

```bash
docker pull junxy/v2ray
```

or

https://github.com/junxy/docker-ray/packages/65576

- 参考官方 `Dockerfile` 制作，目录结构保持不变
    - `/etc/v2ray/config.json`: 配置文件
    - `/usr/bin/v2ray/v2ray`: V2Ray 主程序
    - `/usr/bin/v2ray/v2ctl`: V2Ray 辅助工具
    - `/usr/bin/v2ray/geoip.dat`: IP 数据文件
    - `/usr/bin/v2ray/geosite.dat`: 域名数据文件
- 经过当优化，镜像(压缩)大小仅 `15M` 
