FROM scratch
ADD ubuntu-16.04-beta2-server-cloudimg-amd64-root.tar.gz /
ADD init-fake.conf /etc/init/fake-container-events.conf
ENV container docker
ENV init /sbin/init

RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN echo 'root:docker.io' | chpasswd

EXPOSE 22

CMD ["/sbin/init"]