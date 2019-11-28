# FROM v2ray/official:latest
FROM alpine:latest

LABEL maintainer "Mr. Hsu <junxy@users.noreply.github.com>"

# https://wiki.alpinelinux.org/wiki/Setting_the_timezone
RUN apk add --no-cache tzdata \
    # && ls /usr/share/zoneinfo/Asia \
    && cp /usr/share/zoneinfo/Asia/Taipei /etc/localtime \
    && echo "Asia/Taipei" > /etc/timezone \
    && apk del tzdata

ARG V2RAYVERSION=4.21.3

# https://install.direct/go.sh 
# ref: https://github.com/v2ray/ext/blob/master/docker/official/Dockerfile
RUN wget https://github.com/v2ray/v2ray-core/releases/download/v$V2RAYVERSION/v2ray-linux-64.zip -O /tmp/v2ray.zip \ 
    && mkdir /tmp/v2ray \ 
    && unzip /tmp/v2ray.zip -d /tmp/v2ray \
    && mkdir /usr/bin/v2ray && mkdir /etc/v2ray \
    && cp /tmp/v2ray/v2ray /usr/bin/v2ray/ \
    && cp /tmp/v2ray/v2ctl /usr/bin/v2ray/ \
    && cp /tmp/v2ray/geoip.dat /usr/bin/v2ray/ \
    && cp /tmp/v2ray/geosite.dat /usr/bin/v2ray/ \
    && cp /tmp/v2ray/config.json /etc/v2ray/config.json \
    && rm -rf /tmp/**

RUN set -ex && \
    apk --no-cache add ca-certificates && \
    mkdir /var/log/v2ray/ &&\
    chmod +x /usr/bin/v2ray/v2ctl && \
    chmod +x /usr/bin/v2ray/v2ray

ENV PATH /usr/bin/v2ray:$PATH

# RUN v2ray -version

CMD ["v2ray", "-config=/etc/v2ray/config.json"]