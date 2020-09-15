FROM openjdk:8-jre-alpine

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