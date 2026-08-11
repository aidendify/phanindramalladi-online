# phanindramalladi.online

Personal portfolio for **Phanindra Malladi** — founder of AIdentify.

## Stack

- Static HTML / CSS / JS (no build step)
- Hosted on **GitHub Pages**
- Custom domain: `phanindramalladi.online` (DNS at Hostinger)

## Local preview

```bash
cd portfolio-phanindramadi
python3 -m http.server 8765
# open http://127.0.0.1:8765
```

## Deploy

Push to `main`. GitHub Pages serves from `/` (root).

## Hostinger DNS (apex + www)

Point the domain at GitHub Pages:

| Type | Name | Value | TTL |
|------|------|-------|-----|
| A | `@` | `185.199.108.153` | 3600 |
| A | `@` | `185.199.109.153` | 3600 |
| A | `@` | `185.199.110.153` | 3600 |
| A | `@` | `185.199.111.153` | 3600 |
| CNAME | `www` | `aidendify.github.io` | 3600 |

Remove Hostinger parking / default A records first.

In the GitHub repo: **Settings → Pages → Custom domain** = `phanindramalladi.online`, enable **Enforce HTTPS** after DNS propagates.
