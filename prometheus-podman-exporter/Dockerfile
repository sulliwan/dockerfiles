FROM docker.io/fedora:43
ARG TARGETPLATFORM
ARG TARGETOS
ARG TARGETARCH

RUN dnf install -y prometheus-podman-exporter conmon crun && dnf clean all

EXPOSE 9882
USER nobody
ENTRYPOINT [ "/bin/prometheus-podman-exporter" ]
