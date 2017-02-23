FROM ubuntu:16.04
ENV ROOK_VERSION=v0.2.2
RUN apt-get update && \
    apt-get install -y jq curl && \
    curl -o rook.tgz https://github.com/rook/rook/releases/download/${ROOK_VERSION}/rook-${ROOK_VERSION}-linux-amd64.tar.gz && \
    tar xzvpf rook.tgz -C /usr/bin && \
    chmod +x /usr/bin/rook
COPY storage /usr/bin/
COPY common/common.sh rook/rancher-rook common/start.sh /usr/bin/
CMD ["start.sh", "storage", "--driver-name", "rancher-rook"]
