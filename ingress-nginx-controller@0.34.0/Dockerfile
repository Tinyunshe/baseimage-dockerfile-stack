FROM us.gcr.io/k8s-artifacts-prod/ingress-nginx/controller:v0.34.0@sha256:56633bd00dab33d92ba14c6e709126a762d54a75a6e72437adefeaaca0abb069

USER root

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories && \
    apk update && apk add \
    iproute2 \
    curl \
    busybox-extras \
    tcpdump \
    tzdata
    
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
   echo "Asia/Shanghai" > /etc/timezone && \
   apk del tzdata

USER www-data