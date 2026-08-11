# Hostinger → GitHub Pages (phanindramalladi.online)

GitHub Pages is already live for repo `aidendify/phanindramalladi-online` with custom domain `phanindramalladi.online`. Until DNS changes, the apex still shows Hostinger parking.

## 1. Open Hostinger DNS

1. Log in to [Hostinger hPanel](https://hpanel.hostinger.com/)
2. **Domains** → `phanindramalladi.online` → **DNS / Name Servers**

## 2. Clean parking records

Delete any existing records that point the site at Hostinger parking, especially:

- A / AAAA for `@` (root) pointing at Hostinger IPs (e.g. `2.57.91.91`)
- CNAME for `www` pointing at Hostinger

Keep unrelated records (MX, TXT for email/verification) unless you know they should change.

## 3. Add GitHub Pages records

| Type  | Name | Value / points to     | TTL  |
|-------|------|------------------------|------|
| A     | `@`  | `185.199.108.153`      | 3600 |
| A     | `@`  | `185.199.109.153`      | 3600 |
| A     | `@`  | `185.199.110.153`      | 3600 |
| A     | `@`  | `185.199.111.153`      | 3600 |
| CNAME | `www`| `aidendify.github.io`  | 3600 |

Optional IPv6 (AAAA) for `@`:

- `2606:50c0:8000::153`
- `2606:50c0:8001::153`
- `2606:50c0:8002::153`
- `2606:50c0:8003::153`

## 4. HTTPS on GitHub

After DNS propagates (often 5–60 min; up to 24–48h):

1. Open https://github.com/aidendify/phanindramalladi-online/settings/pages  
2. Confirm **Custom domain** = `phanindramalladi.online` (DNS check should go green)  
3. Enable **Enforce HTTPS**

## 5. Verify

```bash
dig +short phanindramalladi.online A
# should show 185.199.108–111.153

curl -sI https://phanindramalladi.online | head
# title should be Phanindra Malladi — Founder, AIdentify
```

## Email note

The site links `hello@phanindramalladi.online`. Create that mailbox or a forwarder in Hostinger **Emails**, or change the mailto on the site.
