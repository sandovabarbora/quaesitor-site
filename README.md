# quaesitor.eu

Landing page for qu&aelig;sitor — independent review of AI answers over a data
warehouse.

Self-contained HTML files. Images, scripts and JetBrains Mono are inlined. The
one external request each page makes is the Space Grotesk stylesheet from
Google Fonts; every page declares a fallback stack, so a blocked request
degrades the type rather than the page.

| File | What it is |
|---|---|
| `index.html` | the landing page |
| `report-built.html` | the sample review report it links to |
| `privacy.html` | privacy and legal notice |
| `documentation-finding.html` | published measurement: documentation made the errors smaller, not rarer |
| `silent-failure-rate.html` | published measurement: two models, opposite failure behaviour |
| `why.html` | why this exists |
| `silent-failures/` | longer piece on abstention |

## Deploying to Cloudflare Pages

Connect this repository and leave the build settings empty:

- **Framework preset:** None
- **Build command:** *(blank)*
- **Build output directory:** `/`

Pages serves the files as they are. `index.html` is picked up automatically as
the root document.

## Updating

`index.html`, `privacy.html`, `report-built.html` and
`documentation-finding.html` are generated from templates in the private
project repository (`site/build.py` and `site/finding.py`), which read the
measured run outputs so no figure on a page can drift from the run that
produced it. The build fails rather than publish a sentence its runs no longer
support. Regenerate there, copy the files here, commit.

`why.html`, `silent-failure-rate.html` and `silent-failures/` are written by
hand and edited here.
