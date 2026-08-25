# quaesitor.eu

Landing page for qu&aelig;sitor — independent review of AI answers over a data
warehouse.

Self-contained HTML files. Images, scripts and both faces — JetBrains Mono and
Space Grotesk — are inlined as data URIs. A page makes no request to anyone but
the server that served it, which is what `privacy.html` promises.

That was not true until 2026-08-25. Space Grotesk was linked from Google Fonts
and preconnected, so every visitor's IP reached Google, and JetBrains Mono was
named in the stylesheet without ever being supplied. This README described the
Google Fonts request correctly while the privacy notice denied it; the notice
is the document with legal weight, so the code was changed to match it rather
than the other way round. `method/tests/test_no_external_requests.py` reads
these deployed files and fails if any of it comes back.

| File | What it is |
|---|---|
| `index.html` | the landing page |
| `method.html` | the four layers, the packs, the languages finding |
| `faq.html` | the thirteen objections |
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

`index.html`, `method.html`, `faq.html`, `privacy.html`, `report-built.html`
and `documentation-finding.html` are generated from templates in the private
project repository (`site/build.py` and `site/finding.py`), which read the
measured run outputs so no figure on a page can drift from the run that
produced it. The build fails rather than publish a sentence its runs no longer
support. Regenerate there, copy the files here, commit.

`why.html`, `silent-failure-rate.html` and `silent-failures/` are written by
hand and edited here.
