This container provides [caddy-dns](https://github.com/caddy-dns) images with [Tailscale](https://github.com/tailscale/caddy-tailscale) support.

It is straightforward to [build Caddy images with custom plugins](https://caddyserver.com/docs/build#docker) yourself if you have particular plugin requirements, but rebuilding is slow and shouldn't be on the critical path for updates.

Currently images for the following DNS plugins are provided, the top four by GitHub Stars:

* [cloudflare](https://github.com/caddy-dns/cloudflare)
* [porkbun](https://github.com/caddy-dns/porkbun)
* [duckdns](https://github.com/caddy-dns/duckdns)
* [route53](https://github.com/caddy-dns/route53)

It should be straightforward to add more plugins to the build, assuming it does not starve the repo's GitHub action quota.

Images are versioned using the Caddy version number, suffixed by the included DNS provider. For example:

> [!WARNING]
> Caddy plugins are not generally versioned, therefore tags are not guaranteed to be stable across rebuilds.
> For full stability use the image's hash rather than a tag.

* `caddy-ts-dns:2-cloudflare`
* `caddy-ts-dns:2.11-porkbun`
* `caddy-ts-dns:2.11.4-duckdns`