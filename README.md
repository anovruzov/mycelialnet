# Mycelic website

Static website for Mycelic Labs. The site is contained in `index.html` and has no build step or external runtime dependencies.

## Preview

Open `index.html` in a browser, or serve the repository with any static web server.

## Deployment

Publish the repository root using a static host. The entry point is `index.html`.

Cloudflare Workers settings (recommended for the current dashboard):
- Worker name: `mycelium`
- Production branch: `main`
- Root directory: `/`
- Build command: leave blank
- Deploy command: `npx wrangler deploy`

`wrangler.jsonc` serves the root `index.html` directly. `.assetsignore` excludes all other repository files from the public asset upload.

After deployment, add `myceliclabs.com` under Worker Settings > Domains & Routes > Add > Custom Domain.

Cloudflare Pages settings (alternative):
- Production branch: `main`
- Framework preset: None
- Build command: `exit 0`
- Build output directory: `.`

## Website behavior

- Security, Memory, and Discovery simulations play automatically after one click.
- Simulations and latency estimates are browser illustrations, not live agents or measured benchmarks.
- NeuralGraph is the open-source Memory layer. Other ingestion streams are marked as planned.
- The contact form prepares an email draft for Gmail, a mail app, or copying. It does not send email through a backend.
