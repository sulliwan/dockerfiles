FROM --platform=${BUILDPLATFORM} docker.io/node:24 AS builder

# Clone and build Excalidraw
WORKDIR /build
RUN git clone https://github.com/excalidraw/excalidraw.git
WORKDIR /build/excalidraw
RUN npm_config_target_arch=${TARGETARCH} yarn --frozen-lockfile --network-timeout 600000
ARG NODE_ENV=production
RUN npm_config_target_arch=${TARGETARCH} yarn build:app:docker

FROM ghcr.io/static-web-server/static-web-server:2

COPY --from=builder /build/excalidraw/excalidraw-app/build /public

