# FromEdwin website

Temporary static “coming soon” page for [fromedwin.com](https://fromedwin.com), deployed to GitHub Pages.

## Local preview

Serve the `public` folder with any static file server, for example:

```bash
python3 -m http.server 8080 --directory public
```

Then open [http://localhost:8080](http://localhost:8080).

## Deployment

Pushes to `main` run [.github/workflows/deploy.yml](.github/workflows/deploy.yml) and publish the contents of `public/` to GitHub Pages.

### One-time GitHub setup

1. In the repo **Settings → Pages**, set **Source** to **GitHub Actions**.
2. Under **Custom domain**, enter `fromedwin.com` and enable **Enforce HTTPS** once DNS is verified.
3. At your DNS provider, add:
   - **A** records for `@` pointing to GitHub Pages IPs:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - Or a **CNAME** for `www` → `fromedwin.github.io` (if you use `www`; apex still needs A records or ALIAS/ANAME).

The `public/CNAME` file is included in each deploy so GitHub Pages keeps the custom domain configured.
