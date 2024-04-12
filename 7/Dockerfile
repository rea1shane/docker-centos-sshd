FROM centos:7

RUN yum -y update \
    && yum -y install openssh-server \
    && yum clean all \
    && rm -rf /var/cache/yum

# Fix Unable to load host key: ssh_host_rsa_key, ssh_host_ecdsa_key, ssh_host_ed25519_key
RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N '' \
    && ssh-keygen -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key -N '' \
    && ssh-keygen -t ed25519 -f /etc/ssh/ssh_host_ed25519_key -N ''

ARG ROOT_PASSWORD=1
RUN echo "root:${ROOT_PASSWORD}" | chpasswd

# Output sshd logs: https://serverfault.com/questions/952391/sshd-logs-in-docker-container-not-shown-by-docker-logs
CMD ["/usr/sbin/sshd", "-D", "-e"]
