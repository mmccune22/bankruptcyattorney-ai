# Working in bankruptcyattorney-ai

Read `README.md` and inspect `git status` before editing. This repository is Matt's personal static website; it is separate from the corporate BK FastPass site and the BK FastLane application.

- Refresh from current GitHub source, preserving unfinished edits. Do not deploy a stale Claude artifact over newer source.
- Edit only requested files. Review the diff and stage named files. Do not commit secrets or client data, and never force-push shared branches.
- Matt's authorized pushes to `main` or a topic branch produce automatic Cloudflare previews. Report the successful preview link and exact commit SHA. A topic PR into `main` is preferred for a distinct reviewable change.
- Preserve the production `404.html`, `_headers`, both photos, canonical URL and unrelated content. The launch safeguards still need reconciliation into main through the existing PR; do not drop them when packaging a release.
- Check desktop/mobile, light/dark, images, contact and podcast/demo links, and media expand/collapse. This static site has no npm build step.
- Chief's hourly monitor is read-only. It summarizes new evidence and asks Jimmy once to approve a specific site and full SHA, remaining quiet when nothing actionable changes. It never merges, advances a branch or publishes.
- `codex/production` is Cloudflare's production branch with automatic deployment enabled. Only an executor explicitly authorized by Jimmy for the exact reviewed SHA may fast-forward that branch. Require current production history and files to be retained; no force-pushes, no newer unapproved SHA substitutions. Cloudflare's native GitHub integration performs publication without a routine dashboard login.
- The release branch is unprotected; this approval boundary is an operating rule, not a technical Jimmy-only restriction. Do not claim otherwise.
- A request to edit or preview is not approval to publish. Do not merge, update `codex/production`, change hosting/DNS/access settings or create credentials without authorization for that action. Report publication only after checking Cloudflare's deployment SHA and the live pages. Follow the release and rollback guidance in `README.md`.
