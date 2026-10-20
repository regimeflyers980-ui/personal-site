# personal-site

Fanuel Mutua Nduku — portfolio site. Static HTML + CSS.

## Files

- `index.html` — landing page
- `uims.html` — UIMS project case study
- `styles.css` — shared stylesheet
- `README.md` — this file

## Deployment — GitHub Pages

The site is designed to be served as static files from a GitHub repository.
No build step, no dependencies.

To publish:

1. `git init && git add . && git commit -m "initial commit"`
2. Create a repository on GitHub (public — the site needs to be public
   for Pages on the free tier; a future custom domain can change this).
   Suggested name: `personal-site`.
3. `git remote add origin <repo-url>`
4. `git push -u origin main`
5. On GitHub: **Settings → Pages → Build and deployment → Source:
   Deploy from a branch → Branch: main / root → Save**
6. Wait ~60 seconds. Site lives at:
   `https://<username>.github.io/personal-site/`

If the repo is named `<username>.github.io` instead of `personal-site`,
the site lives at `https://<username>.github.io/` (root domain). Either
is fine; the subpath is more flexible for future projects.

## What is NOT linked from here

The billing-service admin dashboard is intentionally not linked from
this site. Reasons:

- An "admin" or "billing" link on a public portfolio is a magnet for
  scrapers and credential-stuffing attacks.
- The admin surface is private by design; it should be reached by
  bookmark or internal tooling, not by hyperlink.

If a future version of this site needs an admin entry point, use a
hard-to-guess path and rely on authentication, not obscurity, for
actual security.

## Custom domain

Later, if a domain is purchased:

1. Add a file `CNAME` containing the bare domain (e.g. `fanuel.dev`).
2. Point the domain's DNS A/AAAA records to GitHub Pages' IPs
   (`185.199.108.153` etc.).
3. In GitHub repo **Settings → Pages**, set the custom domain.
4. Enable "Enforce HTTPS".

No code changes needed.

## Local preview

Open `index.html` directly in a browser. `file://` works fine because
there are no fetch calls or build steps.
