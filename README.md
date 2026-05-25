# saadsid.ai

The personal site of [Saad Siddique](https://github.com/saad770) — AI strategy, frontier
transformation, and design systems.

🌐 **Live:** [saadsid.ai](https://saadsid.ai)

---

## Stack

- **Hosting:** GitHub Pages (deploy from `main` branch, root)
- **DNS:** Cloudflare (free tier)
- **Domain:** `saadsid.ai` via Porkbun / Cloudflare Registrar
- **Build:** None — single self-contained `index.html`, no toolchain, no dependencies

## Design system

Built on the [SaadSid.AI HTML Presentation Kit](../design-system) — a zero-dependency, single-file
HTML design system. All tokens, components, and the conic-gradient brand mark live there.

To regenerate the matching PowerPoint deck:

```powershell
cd ../design-system
python build_deck.py
```

## Local preview

No build step. Just open `index.html` in a browser, or serve it locally:

```powershell
# From this folder
python -m http.server 8000
# then open http://localhost:8000
```

## Deploying

Push to `main`. GitHub Pages does the rest.

```powershell
git add .
git commit -m "Update site"
git push
```

## Custom-domain setup (one-time)

1. Repo → **Settings → Pages → Custom domain** → `saadsid.ai`
2. In Cloudflare DNS, add `A` records for the apex pointing to GitHub's Pages IPs:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   (plus the `AAAA` records for IPv6, and a `CNAME` for `www`)
3. Wait ~10 min, then enable **Enforce HTTPS** in repo settings

---

## License

Content © Saad Siddique. Code under [MIT](LICENSE).
