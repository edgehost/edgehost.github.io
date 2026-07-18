# edgeHOST — public site

The public marketing/product site for **edgeHOST**, the deployment-pipeline
product. Plain static HTML/CSS — no build step — because this is the
GitHub-Pages dogfood target for the edgeHOST deploy pipeline itself (edgeHOST's
first real deploy is its own site).

## Canonical vs deploy

- **Canonical source** (this directory) is **local-first** — it lives in the
  `@projects/@edgehost` bucket and its git remote of record is **local Gitea**
  (`edgehost/edgehost.github.io`). Never author against the deploy target.
- **Deploy target** is **GitHub Pages** — pushed to `github.com` *only when ready
  to deploy*, through the edgeHOST pipeline (`deploy_publish`, `target:
  github-pages`). The site is public; that push is deploying, not a source leak.
  See `@projects/@edgehost/AGENTS.md` and the local-first doctrine.

## Notes

- Directory named `edgehost.github.io` after the phase-1 deploy target
  (`edgehost.github.io`). If a custom apex domain is later attached (via the
  Cloudflare skill), rename to that apex and add a `CNAME`.
- Built as part of `.praxis/changes/edgehost-deploy-phase-1` — the first
  vertical slice of the deploy pipeline.
