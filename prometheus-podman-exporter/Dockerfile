FROM docker.io/fedora:44
ARG TARGETPLATFORM
ARG TARGETOS
ARG TARGETARCH

RUN dnf install -y prometheus-podman-exporter conmon crun && dnf clean all

EXPOSE 9882
USER nobody
ENTRYPOINT [ "/bin/prometheus-podman-exporter" ]
