FROM docker.io/node:24

WORKDIR /app

# Enable pnpm (version pinned by the packageManager field in package.json)
RUN corepack enable

# Clone the repository
RUN git clone https://github.com/openauthenticator-app/backend.git
WORKDIR /app/backend

# Install and build, per the README
RUN pnpm install
RUN pnpm build

EXPOSE 3000

CMD ["pnpm", "start"]
