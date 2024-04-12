FROM centos:8

# Fix yum update error: https://techglimpse.com/failed-metadata-repo-appstream-centos-8/
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* \
    && sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* \
    && yum -y update \
    && yum -y install openssh-server \
    && yum clean all

# Fix Unable to load host key: ssh_host_rsa_key, ssh_host_ecdsa_key, ssh_host_ed25519_key
RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N '' \
    && ssh-keygen -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key -N '' \
    && ssh-keygen -t ed25519 -f /etc/ssh/ssh_host_ed25519_key -N ''

ARG ROOT_PASSWORD=1
RUN echo "root:${ROOT_PASSWORD}" | chpasswd \
    && rm /run/nologin # Remove warning: https://unix.stackexchange.com/questions/487742/system-is-booting-up-unprivileged-users-are-not-permitted-to-log-in-yet

# Output sshd logs: https://serverfault.com/questions/952391/sshd-logs-in-docker-container-not-shown-by-docker-logs
CMD ["/usr/sbin/sshd", "-D", "-e"]
