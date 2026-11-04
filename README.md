# ernirajan.com.np

Static portfolio for **Nirajan Paudel** (structural engineer, Pokhara). Hosted on **Cloudflare Pages** at [ernirajan.com.np](https://ernirajan.com.np).

## Edit content

1. Update **`site-content.json`** (copy, projects, services, links, image paths).
2. Add or replace files under **`images/`**.
3. After JSON edits, sync the embedded block in **`index.html`** (`#site-data`) if you rely on `file://` preview — on the live site, `fetch('site-content.json')` is enough.
4. Commit and push to **`main`** — Cloudflare Pages redeploys automatically.

Intake questionnaire for Nirajan: **`QUESTIONNAIRE-FOR-NIRAJAN.md`**.

## Local preview

```bash
python3 -m http.server 8080
```

Open http://localhost:8080 (serves `site-content.json` correctly).

## GitHub

- **Repo:** [github.com/shreejanpandit/ernirajan](https://github.com/shreejanpandit/ernirajan)
- **Account:** personal GitHub (`shreejanpandit`)

```bash
git push origin main
```

## Cloudflare Pages (one-time setup)

1. Sign in at [dash.cloudflare.com](https://dash.cloudflare.com) (same email as your Cloudflare account).
2. **Workers & Pages** → **Create** → **Pages** → **Connect to Git** → authorize GitHub → select **`shreejanpandit/ernirajan`**.
3. **Build settings**
   - Framework preset: **None**
   - Build command: *(empty)*
   - Build output directory: **`/`** (project root)
   - Production branch: **`main`**
4. **Save and deploy**. Note the `*.pages.dev` URL; confirm the site loads.
5. **Custom domains** → **Set up a custom domain** → add **`ernirajan.com.np`** and optionally **`www.ernirajan.com.np`**.

## DNS — Mercantile (`register.com.np`)

Domain **ernirajan.com.np** is registered at Mercantile (status **Active**).

**Recommended:** use Cloudflare nameservers so Pages SSL and DNS stay in one place.

1. In Cloudflare, add zone **`ernirajan.com.np`** (Free plan) if not already added.
2. Cloudflare shows two nameservers (e.g. `ada.ns.cloudflare.com`, `bob.ns.cloudflare.com` — use **your** assigned pair).
3. At [register.com.np](https://register.com.np/userdomain) → **Active domain** → **Edit DNS** for **ernirajan.com.np**.
4. Replace Mercantile nameservers with Cloudflare’s two nameservers. Save.
5. Wait for propagation (often 1–24 hours; `.com.np` can take longer). Cloudflare will show **Active** when DNS is correct.
6. In **Pages** → your project → **Custom domains**, confirm **Active** / certificate issued.

If Mercantile only allows **records** (not full NS change), add what Cloudflare Pages lists for the custom domain (often a **CNAME** for `www` and guidance for apex `@`). Apex on some registrars needs an **A** record to Cloudflare’s proxy IPs — follow the exact records shown in the Pages custom-domain wizard.

## Pages settings checklist

| Setting | Value |
|--------|--------|
| Root files | `index.html`, `site-content.json`, `images/` |
| Build | None |
| Output | `/` |
| Node version | Default (not required) |

## Privacy

Mobile numbers are not shown on the page. Contact uses **email**, **WhatsApp**, and **Viber** links; office landline stays off unless `showLandlineOnSite` is `true` in JSON.
