# Personal site — sergii danyliuk

Single-page, plain HTML/CSS with one small first-party script (theme toggle).
Built 2026-08-17 to close item 5 of the 2026-08-13 resume review (personal site
on the contact line). Redesigned same day in an editorial style (sticky nav,
statement headline, stat band, numbered case studies) per owner direction.

## Files

- `index.html` — the whole site (includes the ~15-line theme-toggle script)
- `style.css` — styling; dark by default, light via system preference or toggle
- `headshot.jpg` — owner photo (800px, optimized)
- `resume.pdf` — downloadable résumé linked from the hero and footer
- `CNAME` — custom domain (sergii-dan.info)
- `.github/workflows/deploy.yml` — GitHub Actions deploy to GitHub Pages

## Deploy (one-time setup)

1. Create a new **public** GitHub repo (any name, e.g. `personal-site`).
2. Copy the contents of this `website/` folder to the repo root (including the
   hidden `.github/` folder) and push to `main`.
3. In the repo: **Settings → Pages → Source: GitHub Actions.**
4. The workflow deploys on every push to `main`.

## Custom domain

Domain: **sergii-dan.info** (owner-confirmed 2026-08-17). The `CNAME` file in
this folder already contains it — just copy it along with everything else.

1. In **Settings → Pages → Custom domain**, enter `sergii-dan.info` and keep
   **Enforce HTTPS** checked once the cert is issued.
2. At the DNS provider for `sergii-dan.info`:
   - apex (`sergii-dan.info`): `A` records to GitHub Pages IPs
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - optional `www`: `CNAME` record to `<github-username>.github.io`
4. After it's live: add the URL to the contact line in `resume/resume.md`,
   note it in `resume/comments.md` (item 5), and flip `resume/status.md`
   to `review-ready`.

## Local preview

```bash
python3 -m http.server 8123 --directory website
```

Then open http://localhost:8123.
