# FROM v2ray/official:latest
FROM alpine:latest

LABEL maintainer "Mr. Hsu <junxy@users.noreply.github.com>"

# https://wiki.alpinelinux.org/wiki/Setting_the_timezone
RUN apk add --no-cache tzdata ca-certificates \
    # && ls /usr/share/zoneinfo/Asia \
    && cp /usr/share/zoneinfo/Asia/Taipei /etc/localtime \
    && echo "Asia/Taipei" > /etc/timezone \
    && apk del tzdata

ARG V2RAYVERSION=4.22.1
# https://microbadger.com/labels
ARG VCS_REF=${VCS_REF}
ARG VCS_REF2=${VCS_REF2}
ARG VCS_REF3=${VCS_REF3}
LABEL org.label-schema.vcs-ref=$VCS_REF \
        org.label-schema.vcs-url="https://github.com/junxy/docker-ray"

RUN echo test123$VCS_REF
RUN echo test123$VCS_REF2
RUN echo test123$VCS_REF3
RUN echo ${env.GITHUB_SHA_SHORT}

# https://install.direct/go.sh 
# ref: https://github.com/v2ray/ext/blob/master/docker/official/Dockerfile
RUN set -ex \ 
    && wget https://github.com/v2ray/v2ray-core/releases/download/v$V2RAYVERSION/v2ray-linux-64.zip -O /tmp/v2ray.zip \ 
    && mkdir /tmp/v2ray \ 
    && unzip /tmp/v2ray.zip -d /tmp/v2ray \ 
    && mkdir /usr/bin/v2ray \ 
    && mkdir /etc/v2ray \ 
    && mkdir /var/log/v2ray/ \
    && cp /tmp/v2ray/v2ray /usr/bin/v2ray/ \ 
    && cp /tmp/v2ray/v2ctl /usr/bin/v2ray/ \ 
    && cp /tmp/v2ray/geoip.dat /usr/bin/v2ray/ \ 
    && cp /tmp/v2ray/geosite.dat /usr/bin/v2ray/ \ 
    && cp /tmp/v2ray/config.json /etc/v2ray/config.json \ 
    && chmod +x /usr/bin/v2ray/v2ctl \
    && chmod +x /usr/bin/v2ray/v2ray \
    && rm -rf /tmp/**

ENV PATH /usr/bin/v2ray:$PATH

# test 
RUN v2ray -version

CMD ["v2ray", "-config=/etc/v2ray/config.json"]