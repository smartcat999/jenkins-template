FROM alpine:edge as base

RUN echo "http://dl-cdn.alpinelinux.org/alpine/edge/main" >> /etc/apk/repositories && \
    sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories

RUN apk add shadow && \
    usermod -s /sbin/nologin -g nogroup sync && \
    usermod -s /sbin/nologin -g nogroup shutdown && \
    usermod -s /sbin/nologin -g nogroup halt && \
    apk del shadow

RUN apk update && \
    apk --no-cache upgrade --available && \
    sync && \
    rm /var/cache/apk/*

RUN rm /usr/bin/id && find /etc ! -perm 600 -name "*.crt" -o ! -perm 600 -name "*.pem" 2>/dev/null | xargs -I {} chmod 600 {} && \
    find /etc ! -perm 640 -name "*.conf" 2>/dev/null | grep -v "/etc/resolv.conf" | xargs -I {} chmod 640 {} && \
    find /usr ! -perm 600 -name "*.crt" -o ! -perm 600 -name "*.pem" 2>/dev/null | xargs -I {} chmod 600 {} && \
    find /usr ! -perm 640 -name "*.conf" 2>/dev/null | xargs -I {} chmod 640 {} && \
    rm /etc/ssl/cert.pem && rm -rf /etc/ssl/certs/


FROM scratch

COPY --from=base / /

CMD ["sh"]
