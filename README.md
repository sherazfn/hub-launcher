# hub-launcher

A tiny public "launcher" page for my tailnet-only home automation hub.

The hub ([`sherazfn/home-automation`](https://github.com/sherazfn/home-automation), private)
is fronted by **Tailscale Serve** and is reachable **only** over my tailnet. When
Tailscale is off, the hub URL just times out with a generic browser error — easy to
forget why. This page is hosted publicly (GitHub Pages), so it *always* loads. It:

- reminds me the hub needs Tailscale **on**, and
- probes the hub: if it's reachable (Tailscale on) it auto-opens; otherwise it shows
  the reminder and an **Open Hub** button.

Bookmark the Pages URL instead of the raw `*.ts.net` hub URL.

## Security notes

- **No secrets here.** It links to the *bare* hub URL only — never any path/query
  password. This repo is public; nothing sensitive goes in it.
- The only thing disclosed is the hub's MagicDNS hostname, which is already public
  via Certificate Transparency logs. Knowing the name grants no access — the hub
  stays unroutable to anyone not on the tailnet.
- `noindex` keeps it out of search results.
