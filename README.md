# chaidev

Public docs and the lightweight site that serves them for the ChAIDev community.

## What's here

- **`community-design.md`** — the working doc for ChAIDev. Mission, vibe, ground rules, the meeting, the Slack, how new members join. Canonical source of truth.
- **`community-moderation.md`** — a more general field guide on community moderation for small invite-only groups. Research synthesis. Useful reading for anyone running or thinking of running a similar community.
- **`static/`** — the Google App Engine site (`chaidev-2026.uc.r.appspot.com`) that renders the markdown above.
- **`app.yaml` / `main.py`** — GAE deploy config.

## Proposing changes

Both documents live in this repo because they're meant to be reviewable, forkable, and PR-able. If you see something worth changing — typo, fact, framing, missing nuance — open a PR. Substantive changes get discussed in the PR thread; small ones can be merged once they look right.

## Running locally

The site is plain static HTML + client-side markdown rendering via `marked.js` (loaded from CDN). To preview locally:

```bash
cd static
python3 -m http.server 8080
# then visit http://localhost:8080
```

Note: when running locally the markdown files won't be served by the `python -m http.server` command unless you also serve them from the `static/` directory or run from the repo root. For full fidelity, deploy to GAE.

## Deploying

App Engine standard, Python 3.11 runtime. Deploy with:

```bash
gcloud app deploy app.yaml --project=chaidev-2026
```

Requires `gcloud` authenticated and the project set. The site lives at `https://chaidev-2026.uc.r.appspot.com`.

## License

The docs are intentionally public for transparency and to enable community contribution. No formal license attached yet — if you want to reuse content, please ask.
