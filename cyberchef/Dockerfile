FROM --platform=${BUILDPLATFORM} docker.io/node:24 AS builder

# Clone and build CyberChef
WORKDIR /build
RUN git clone https://github.com/gchq/CyberChef.git
WORKDIR /build/CyberChef
RUN npm ci --ignore-scripts
RUN npm run postinstall
RUN npm run build

FROM ghcr.io/static-web-server/static-web-server:2

COPY --from=builder /build/CyberChef/build/prod /public

