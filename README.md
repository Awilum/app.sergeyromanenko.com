# app.sergeyromanenko.com

Deployment artifact for the applications workspace at <https://app.sergeyromanenko.com>.

This repository holds generated static files only. The source project is
[`Awilum/app.sergeyromanenko.src`](https://github.com/Awilum/app.sergeyromanenko.src);
running `npm run build` there cleans this checkout and rebuilds it in place.
Do not edit the generated files by hand.

## Deploying to Cloudflare Pages

Connect this repository to a Cloudflare Pages project in the Workers & Pages
dashboard:

- Production branch: `master`
- Build command: none (the files here are already built)
- Output directory: `/` (the repository root)

`wrangler.toml` records the same output directory for `wrangler pages deploy`
and for local preview with `wrangler pages dev`.

Point `app.sergeyromanenko.com` at the Pages project from the dashboard's
**Custom domains** tab and let Cloudflare manage the DNS record. A `CNAME` file
is not used: unlike GitHub Pages, Cloudflare configures custom domains outside
the repository.

## Crawl configuration

`robots.txt` allows crawling, and `sitemap-index.xml` lists the launcher and the
three legal pages. Runtime routes under `/apps/` carry `noindex, follow` in
their HTML but remain crawlable so search engines can read that directive.

## Files kept by the repository

`wrangler.toml`, this README and Git metadata survive every rebuild. All other
files are recreated from the source project.
