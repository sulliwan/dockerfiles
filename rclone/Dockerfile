FROM docker.io/fedora:44
ARG TARGETPLATFORM
ARG TARGETOS
ARG TARGETARCH

RUN dnf install -y rclone && dnf clean all

USER nobody
ENTRYPOINT [ "/bin/rclone" ]