# ESE Collective website

Static site: `index.html`, `terms.html`, `privacy.html`, `assets/`. No frameworks, no trackers.

## TODO before going live
- `index.html`: replace the `#` Discord button link with the real invite link.
- `terms.html` / `privacy.html`: confirm `contact@esecollective.com` exists (set up email forwarding), then remove the TODO tags.

Discord Developer Portal URLs after hosting:
- Terms: `https://esecollective.com/terms.html`
- Privacy: `https://esecollective.com/privacy.html`

## Free hosting with a custom domain

### 1. GitHub Pages
1. Create a public repo (for example `ese-site`) and upload these files to the root.
2. Settings → Pages → Source: deploy from branch `main`, folder `/ (root)`.
3. Under Custom domain, enter `esecollective.com` (this creates a `CNAME` file).
4. At your registrar's DNS, add A records for `@` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, and a CNAME for `www` → `<username>.github.io`.
5. Once DNS works, tick **Enforce HTTPS**.

### 2. Cloudflare Pages
1. Cloudflare dashboard → Workers & Pages → Create → Pages → **Upload assets**, and upload the folder or zip (or connect the GitHub repo).
2. Project → Custom domains → add `esecollective.com` (and `www`).
3. If the domain's DNS is on Cloudflare, records are added automatically. If not, add the CNAME it shows you, or move nameservers to Cloudflare (this also gives free Email Routing for contact@).

### 3. Netlify
1. app.netlify.com → Add new site → **Deploy manually**, then drag this folder in (or import from Git).
2. Domain management → Add a domain → `esecollective.com`.
3. Either use Netlify DNS (change nameservers at the registrar) or add an A record `@` → `75.2.60.5` and a CNAME `www` → `<site>.netlify.app`.
4. HTTPS is issued automatically (Let's Encrypt).
