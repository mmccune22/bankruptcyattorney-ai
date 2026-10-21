# BankruptcyAttorney.ai

Matt McCune's personal website. Source: [mmccune22/bankruptcyattorney-ai](https://github.com/mmccune22/bankruptcyattorney-ai). Live site: [bankruptcyattorney.ai](https://bankruptcyattorney.ai/).

## Edit and preview

Refresh your local checkout or Claude artifact from current GitHub source before editing; preserve unfinished changes separately. An older artifact does not automatically include website fixes made later. Edit `index.html` and the intended assets, review the diff, and commit only the named files. Do not commit credentials or client data, or force-push shared branches.

Matt can push a working branch and open a pull request into `main`, or push an authorized source update to `main`. All nonproduction branches, including `main`, receive automatic Cloudflare previews. Use the successful Cloudflare check's preview link and exact SHA when requesting review. These pushes do not publish the live website.

This is a static HTML site with no package build. Check the page on desktop and mobile, its light/dark appearance, photos, contact links, Speaking and Media links, and the Show all/Show fewer interaction. The media entries live in the `MEDIA` array in `index.html`, newest first. For podcast entries, `url` is the episode page and optional `video` is the demo link.

## Preserve production files

The current launch source includes `404.html` and `_headers` on `matt/attorney-launch`. They provide the branded missing-page response, security headers and Pages-host noindex rules. They must be reconciled into the authoring source and retained in every release. [Draft PR #1](https://github.com/mmccune22/bankruptcyattorney-ai/pull/1) proposes that reconciliation. Do not replace the production file set with only `index.html` and the two photographs.

The October 21 podcast candidate `codex/podcast-release` at `6cd2d76f63c166ffba3a9ecb4eebb8dac415cc3b` combines Matt's episode/demo changes with those existing launch files. Preparing a candidate does not authorize publication.

## Review and release

| Setting | Value |
| --- | --- |
| Cloudflare Pages project | `bankruptcyattorney-ai` |
| Production branch | `codex/production` |
| Automatic production deployment | Enabled for `codex/production` |
| Preview branches | All nonproduction branches, including `main` |
| Public domain | `https://bankruptcyattorney.ai/` |

Chief's hourly release monitor reads GitHub changes, available build checks and deployment evidence. It stays quiet when nothing actionable changes and notifies Jimmy once for a new candidate, with the site, full SHA, preview URL, change summary and blockers. The monitor does not merge, push the release branch or deploy. Silence is not approval. A source push or passing check alone does not prove that the public website changed.

Jimmy approves the specific previewed version. An authorized executor then fetches current refs, verifies that the approved SHA includes the current production history and required files, and fast-forwards `codex/production` to that exact SHA with a normal, non-force push. If that cannot fast-forward, reconcile the source and review the new SHA before approval. Later commits require their own review; do not substitute the latest tip for an approved SHA.

Cloudflare's existing GitHub integration builds and publishes the release-branch push. Routine releases need authenticated GitHub access but do not require a new Cloudflare dashboard login or a deployment token in the repository. Revoked integration access or account recovery can still require sign-in.

The release branch is unprotected. Approval is an operating rule, not a technical Jimmy-only gate: another collaborator with write access can push it. Never push `codex/production` during ordinary authoring.

After a release, record Cloudflare's deployment ID, URL and source SHA. Verify the public homepage, both photos, new links, `www` redirect, branded 404 and response headers before reporting completion. Keep the previous successful production deployment as the rollback reference. A Cloudflare rollback or any DNS/account-setting change needs separate explicit authorization; never rewrite release history to roll back.

References: [Cloudflare branch controls](https://developers.cloudflare.com/pages/configuration/branch-build-controls/) and [preview deployments](https://developers.cloudflare.com/pages/configuration/preview-deployments/).
