FROM local/c7-systemd

WORKDIR /nordlayer

ADD . /nordlayer

VOLUME ["/sys/fs/cgroup"]

RUN yum -y install /nordlayer/nordlayer-latest-1.0.0-noarch.rpm; \
    yum -y makecache; \
    yum -y install nordlayer --nogpgcheck;

RUN systemctl enable nordlayer.service; \
    systemctl enable nordlayer.socket


EXPOSE 80:80

CMD ["/usr/sbin/init"]


