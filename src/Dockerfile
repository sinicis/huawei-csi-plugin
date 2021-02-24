FROM centos:centos8.3.2011

LABEL org.opencontainers.image.title="huawei-csi-plugi8n"
LABEL org.opencontainers.image.description="A docker image containing the Huawei CSI plugin for k8s"
LABEL org.opencontainers.image.authors="Adfinis AG <https://adfinis.com>"
LABEL org.opencontainers.image.vendor="Adfinis"
LABEL org.opencontainers.image.url="https://github.com/adfinis-sygroup/huawei-csi-plugin"

RUN yum install -y \ 
device-mapper-multipath \ 
iscsi-initiator-utils \ 
nvme-cli \
xfsprogs \ 
nfs-utils \ 
net-tools \ 
e2fsprogs 

ADD ["bin/huawei-csi", "/"] 
ADD ["bin/passwdEncrypt", "/"] 
RUN ["chmod", "+x", "/huawei-csi"] 
RUN ["chmod", "+x", "/passwdEncrypt"] 

ENTRYPOINT ["/huawei-csi"]
