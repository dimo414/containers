ARG CADDY_VERSION=2.11

FROM caddy:${CADDY_VERSION}-builder-alpine AS builder
ARG DNS_PROVIDER=porkbun
RUN --mount=type=cache,target=/go/pkg/mod \
    --mount=type=cache,target=/root/.cache/go-build \
    xcaddy build \
  --with github.com/tailscale/caddy-tailscale \
  --with github.com/caddy-dns/${DNS_PROVIDER}

FROM caddy:${CADDY_VERSION}
COPY --from=builder /usr/bin/caddy /usr/bin/caddy
