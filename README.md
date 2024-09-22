# tailscale-immich
Updates the official Immich Docker compose file by adding a Tailscale side car so that the Immich server can be shared over the Internet

## Pre-requisites:

* Tailscale account with HTTPS Certificates and Funnel enabled
* Tailscale Funnel security policy that allows for resources with `tag:container`

Example:

```json
"nodeAttrs": [
    {
        "target": ["autogroup:member", "tag:container"],
        "attr":   ["funnel"],
    },
],
```

## Getting started

* Replace the `TS_AUTHKEY` with your Tailscale auth key in `docker-compose.yml`
* Create a `.env` file based on the `example.env` configuring the Immich database credentials and upload location
* Run `docker compose up`

