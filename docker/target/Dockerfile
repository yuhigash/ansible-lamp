FROM centos:centos7

RUN yum -y install openssh-server

RUN ssh-keygen -f /etc/ssh/ssh_host_rsa_key -N '' -t rsa
RUN ssh-keygen -f /etc/ssh/ssh_host_ecdsa_key -N '' -t ecdsa

RUN sed -ri 's/^#PermitEmptyPasswords no/PermitEmptyPasswords yes/' /etc/ssh/sshd_config
RUN echo "root:" | chpasswd

EXPOSE 22
EXPOSE 4630

CMD ["/usr/sbin/sshd", "-D"]
