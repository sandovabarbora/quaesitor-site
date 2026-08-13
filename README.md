# quaesitor.eu

Landing page for Quaesitor — independent audit of AI answers over a data
warehouse.

Two self-contained HTML files. Fonts, images and scripts are inlined, so there
are no external requests and nothing to build.

| File | What it is |
|---|---|
| `index.html` | the landing page |
| `report-built.html` | the sample audit report it links to |

## Deploying to Cloudflare Pages

Connect this repository and leave the build settings empty:

- **Framework preset:** None
- **Build command:** *(blank)*
- **Build output directory:** `/`

Pages serves the files as they are. `index.html` is picked up automatically as
the root document.

## Updating

Both files are generated from templates in the private project repository
(`site/build.py`), which reads the measured run outputs so no figure on the page
can drift from the run that produced it. Regenerate there, copy the two files
here, commit.
