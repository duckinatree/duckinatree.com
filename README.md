# duckinatree.com

Website for duckinatree.com

Static HTML, deployed by GitHub Pages from `main` at the repo root. There is no
build step — **a push to `main` publishes to the live site immediately.**

## `ChurchillResidence/` — do not delete

The Churchill Residence site now lives at its own domain,
[churchillresidence.com](https://churchillresidence.com/) (repo:
`duckinatree/churchillresidence.com`).

The `ChurchillResidence/` folder here is **intentionally kept** so that old
inbound links to `duckinatree.com/ChurchillResidence/...` keep working. Each
page is a redirect stub only — no real content — using a canonical link, a
`<meta http-equiv="refresh">`, and a JS `location.replace()` that forwards any
query string and hash along with the visit.

Leave these files in place. Removing them would break existing links and lose
the SEO value they forward to the new domain.
