FROM local/c7-systemd

WORKDIR /nordlayer

ADD . /nordlayer

VOLUME ["/sys/fs/cgroup"]

RUN yum -y install /nordlayer/nordlayer-latest-1.0.0-noarch.rpm; \
    yum -y makecache; \
    yum -y install nordlayer --nogpgcheck;

# RUN systemctl enable nordlayer.service; \
#     systemctl enable nordlayer.socket


EXPOSE 8080:8080

CMD ["/usr/sbin/init"]


# sudo docker build -t nordlayer ./
# sudo docker run -d --name=nordlayer --rm nordlayer
# sudo docker exec -ti nordlayer /bin/bash
