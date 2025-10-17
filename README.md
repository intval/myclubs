# GitHub Pages deployment

This repository contains a simple static site. These instructions show two ways to publish it via GitHub Pages:

1) Automatic deploy using GitHub Actions (recommended)
2) Manual enable via the repository Settings (simpler for first-time use)

Automatic (GitHub Actions)
- A workflow is included at `.github/workflows/pages.yml` that uploads the repository contents to GitHub Pages on pushes to the `main` branch.
- After pushing to `main`, visit the repository Settings -> Pages to verify the site build and URL.

Manual enable (repository Settings)
1. Go to your repository on GitHub.
2. Settings -> Pages.
3. Under "Build and deployment" choose "Deploy from a branch".
4. Branch: `main`, Folder: `/ (root)`. Save.
5. The site should be available at `https://<your-username>.github.io/<repo-name>/` after a few minutes.

Custom domain (CNAME)
- Add a file named `CNAME` at the repository root containing your custom domain (e.g. `www.example.com`).
- Configure DNS for the domain as described in the GitHub Pages documentation.

Verification and troubleshooting
- If your site doesn't appear, check Actions -> Workflows -> "Deploy to GitHub Pages" for logs.
- In Settings -> Pages check the latest deployment and any reported errors.

Notes
- If your site requires a build step (React, Svelte, etc.) update the workflow to run the build and upload the build output directory (for example `build/` or `dist/`) instead of the repo root.
- The included workflow sets `path: ./` assuming a static site in the repository root (for example `index.html`).
