FROM scratch
ADD xenial-server-cloudimg-amd64-root.tar.gz / 
ADD init-fake.conf /etc/init/fake-container-events.conf
ENV container docker
ENV init /sbin/init

RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN echo 'root:docker.io' | chpasswd

RUN adduser ubuntu
RUN echo ubuntu:ubuntu | chpasswd 
RUN echo 'ubuntu ALL=NOPASSWD: ALL' >> /etc/sudoers
EXPOSE 22

CMD ["/sbin/init"]
