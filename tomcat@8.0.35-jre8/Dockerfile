FROM tomcat:8.0.35-jre8

RUN echo "deb [check-valid-until=no] http://cdn-fastly.deb.debian.org/debian jessie main" > /etc/apt/sources.list.d/jessie.list && \
    echo "deb [check-valid-until=no] http://archive.debian.org/debian jessie-backports main" > /etc/apt/sources.list.d/jessie-backports.list && \
    sed -i '#deb http://deb.debian.org/debian jessie-updates main#d' /etc/apt/sources.list && \
    apt-get -o Acquire::Check-Valid-Until=false update && \
    ln -snf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo "Asia/Shanghai" > /etc/timezone && \
    apt-get -y install tzdata \
                    telnet \
                    curl \
                    net-tools \
                    tcpdump && \
    apt-get -y clean  && \
    apt-get -y autoclean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD lib.tar /usr/local/apr/lib/
# tomcat apr库优化