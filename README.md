# Personal site

Plain HTML and CSS, no build step. Every page can be edited by hand in any text editor.

## Files

| Path | What it is |
|---|---|
| `index.html` | Home: intro, how I work, selected work, what I'm looking for, background, contact |
| `work/c2c-seller-messaging.html` | Case study 1 (eBay seller messaging) |
| `work/_template.html` | Copy this to start a new case study |
| `assets/site.css` | The one stylesheet. Colours and fonts live in the tokens at the top |
| `assets/img/` | Images (put the portrait here as `portrait.jpg`) |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Before going public

1. Photo is in `assets/img/portrait.jpg` (square, 360px). A larger original (800px or more) will look sharper on high-resolution screens.
2. Delete any `<p class="draft-note">…</p>` (search for `draft-note`).
3. Check every claim against READ FIRST §4 and the C2C claims doc.

## Adding a case study

1. Copy `work/_template.html` to `work/<slug>.html` and replace every `[bracketed]` item.
2. In `index.html`, on that project's card: remove `is-pending`, change the status pill to `<span class="status is-ready">Case study</span>`, link the title, and add a "Read the case study" link (copy the C2C card).

## Publishing on GitHub Pages

1. On GitHub, create a public repository named `<your-username>.github.io`.
2. Upload or push these files to the `main` branch, with `index.html` at the top level.
3. Repository → Settings → Pages → Build and deployment: Source "Deploy from a branch", branch `main`, folder `/ (root)`.
4. The site goes live at `https://<your-username>.github.io` within a few minutes.

## Custom domain (when ready)

1. Buy the domain (Cloudflare Registrar or Namecheap; check the renewal price, not just year one).
2. Settings → Pages → Custom domain: enter it (for example `www.yourname.com`). GitHub adds a `CNAME` file to the repo.
3. At the registrar's DNS:
   - `www` → CNAME → `<your-username>.github.io`
   - apex (`yourname.com`) → four A records: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - If using Cloudflare DNS, set these records to "DNS only" (grey cloud) until GitHub issues the certificate.
4. Once the DNS check passes, tick "Enforce HTTPS".
