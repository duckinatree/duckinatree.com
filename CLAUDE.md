# duckinatree.com — notes for Claude

## Never push without asking

The global rule in `~/.claude/CLAUDE.md` applies, and it matters more here
than in most repos: **there is no staging environment and no build step.**
GitHub Pages serves `main` at the repo root, so a push to `main` is
published to the public site within about a minute.

There is no safe "just push and check" — the check happens in public. Commit
the work, report what is staged, and wait to be asked before pushing.

## Verifying a deploy

Two things have produced false readings here, both worth guarding against:

- **Pages lag.** The asset 404s for roughly 15–60s after a push while the
  build runs. A single check straight after pushing proves nothing — poll
  until the new content actually appears.
- **Browser cache.** After a confirmed-good deploy, the browser served the
  previous build and made a shipped change look like it had failed. Confirm
  with `curl` against the live URL, and cache-bust before trusting a
  screenshot.

## Assets must be committed alongside the markup that references them

Commit `1df0928` added an `<img>` pointing at a `crew.jpg` that was never
committed, and the live homepage rendered a broken-image placeholder until
`a45a145` removed it. Images pasted into chat are **not** files on disk and
cannot be saved from there — ask for a path or URL. Verify the asset returns
HTTP 200 on the live site, not just that the commit succeeded.

The `<img>` on the splash page carries an `onerror` handler that falls back
to a centred wordmark, so a missing asset degrades deliberately rather than
showing a broken icon. Keep it.

## ChurchillResidence/ — do not delete

Redirect stubs only, kept so old inbound links keep working. See README.md.
