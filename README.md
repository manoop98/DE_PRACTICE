# Manoop — DevOps Portfolio

Static portfolio site, deployed to GitHub Pages by GitHub Actions on every push to `main`.

## Deploy in 4 steps

1. Create a repo on GitHub. Name it `manoop98.github.io` to get the site at
   `https://manoop98.github.io`, or any other name (e.g. `portfolio`) to get
   `https://manoop98.github.io/portfolio`.
2. Push these files:
   ```bash
   git init
   git add .
   git commit -m "Add portfolio"
   git branch -M main
   git remote add origin https://github.com/manoop98/<repo-name>.git
   git push -u origin main
   ```
3. In the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
4. Open the **Actions** tab, watch `Deploy portfolio to GitHub Pages` go green, and open the URL from the `deploy` job.

## Editing

Everything lives in `index.html`. Search for `EDIT:` comments to find the
spots for your email, LinkedIn, and certification status. Drop a photo or
resume PDF into `assets/` and link it from the page.

## Pipeline

| Job      | What it does                                                   |
|----------|----------------------------------------------------------------|
| `build`  | Checks out code, verifies `index.html`, packages `_site/`       |
| `deploy` | Publishes the artifact to GitHub Pages via OIDC (`id-token`)   |
