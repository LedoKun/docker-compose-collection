FROM caddy:2-builder-alpine AS builder

RUN xcaddy build \
    --with github.com/hslatman/caddy-crowdsec-bouncer \
    --with github.com/hslatman/caddy-crowdsec-bouncer/http \
    --with github.com/hslatman/caddy-crowdsec-bouncer/layer4 \
    --with github.com/greenpau/caddy-security

FROM caddy:2-alpine

COPY --from=builder /usr/bin/caddy /usr/bin/caddy