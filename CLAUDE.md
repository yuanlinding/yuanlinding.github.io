# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Personal academic website for **Linding Yuan** (袁林丁), computational
condensed-matter theorist. Built with the **HugoBlox Academic CV** template
(Hugo v0.161+, schema v2.0). Targeted initial use: research-scientist job
search — content is framed for an industry / AI-for-science audience
(Periodic Labs and similar), not just for academic colleagues.

## Framing rule (load-bearing)

All research content follows **material → testable prediction → what it
enables**. The homepage `Research` markdown block, the project pages under
`content/projects/`, and the publication `summary` fields all stick to this
shape. If you add new content, keep that shape — don't drift back into a
"results-only" academic dump.

## Dev environment

Hugo is *not* in the system `$PATH`. It lives in the conda env `web` along
with Go (needed by `hugo mod`). Tailwind v4 + Pagefind come from `npm`.

```bash
# One-time activation in any new shell:
source /software/miniconda3/4.10.3/etc/profile.d/conda.sh
conda activate web
export PATH="$PWD/node_modules/.bin:$PATH"   # tailwindcss, pagefind
```

Versions known to work: Hugo extended 0.161.1 (conda-forge), Go 1.26, Node
22.18, `@tailwindcss/cli` ^4.1.12, `pagefind` ^1.4.

### Why not the upstream Hugo binary?

The host is RHEL 8 (`glibc 2.28`). Upstream Hugo binaries require
`glibc ≥ 2.29`. Conda-forge ships Hugo with bundled libs that work — keep
using it. Don't bother re-downloading the GitHub release tarball; it will
fail with `libm.so.6: version GLIBC_2.29 not found`.

## Commands

```bash
# Local dev server (livereload, drafts on)
hugo server --disableFastRender
# or:
npm run dev

# Production build (writes to public/)
hugo --gc --minify
# Full build incl. search index:
npm run build

# Re-fetch Hugo modules after a `module.yaml` edit
hugo mod get -u

# Clean caches if blocks/templates seem stale
rm -rf public resources .hugo_build.lock
```

If you see `binary with name "tailwindcss" not found in PATH`, the
`node_modules/.bin` PATH export above was missed.

## Architecture

### Content layout (the things you'll actually edit)

- `data/authors/me.yaml` — **owner profile**. Single source of truth for
  bio, affiliations, education, experience, skills, awards, social links.
  Consumed by `resume-biography-3` (homepage), `resume-experience` (the
  `/experience/` page), and any block that references `username: me`.
- `content/_index.md` — homepage. Three blocks only:
  bio (with `gradient_mesh: false`, `avatar.size: small`), a short
  *Research* markdown blurb linking to `/research/`, and a *News*
  collection over `content/blog/`.
- `content/research/_index.md` + `content/research/<slug>/index.md` —
  **research themes** section. Four themes: magnetism,
  hidden-spin-polarization, direct-bandgap-semiconductors,
  symmetry-tools-for-ai. The landing page uses Hugo's section listing
  (`view: citation`), not a HugoBlox `collection` block — keeps the look
  consistent with `/publications/` and `/talks/`.
- `content/publications/<slug>/index.md` — one folder per paper, 15 
  entries. Landing page `content/publications/_index.md` renders them
  all in one numbered list (no featured/non-featured split since the
  restyle; the `featured: true` flag on six entries is dormant but
  retained in case the split is ever re-enabled).
  Naming convention: `<venue>-<year>-<short-slug>` (e.g.,
  `prb-2020-altermagnet`, `preprint-2025-srfeo3`).
- `content/talks/<slug>/index.md` — invited / contributed talks (12
  entries from the CV). Landing page mirrors `publications/_index.md`
  (`view: citation`).
- `content/blog/<slug>/index.md` — News posts surfaced on the homepage.
  Date-stamped, short summary, optional tags.
- `content/experience.md` — the standalone `/experience/` page. Reads
  from `data/authors/me.yaml`; usually doesn't need editing.

### Configuration

- `config/_default/hugo.yaml` — Hugo-level settings (title, `baseURL`,
  CJK on). Update `baseURL` before deploying.
- `config/_default/params.yaml` — HugoBlox schema v2 config: identity,
  theme, colors, analytics, search, comments. Math rendering is enabled
  here (needed for $...$ in research text).
- `config/_default/menus.yaml` — the navbar. Anchors (`/#research`) map
  to `id:` fields in `content/_index.md` blocks.
- `config/_default/module.yaml` — Hugo module imports (HugoBlox kit).

### Blocks

The homepage is composed of three HugoBlox blocks:

- `resume-biography-3` — small-avatar hero. Gradient mesh disabled.
- `markdown` — the *Research* blurb linking to `/research/`.
- `collection` — *News* feed over `content/blog/`, citation view.

Section landing pages (`/research/`, `/publications/`, `/talks/`) use
Hugo's section-listing template with `view: citation` in frontmatter —
**not** HugoBlox landing/`collection` blocks. The kit's section listing
respects `pagination.pagerSize` in `hugo.yaml` (currently 50 — wide
enough to fit every paper / talk on a single page; bump if it grows).

There is **no `contact` block** in the kit at v2.0 — use a `markdown`
block instead. (An earlier attempt used `block: contact` and crashed the
build.)

### Visual overrides

The minimal-style restyle is driven by:

1. `config/_default/params.yaml` — `header.style: navbar-simple`,
   `header.search/theme_toggle/theme_picker/language_switcher` all
   `false`, `footer.style: minimal`, `theme.mode: light`, primary color
   `#4E2A84` (Northwestern purple), `layout.spacing: comfortable`.
2. `config/_default/menus.yaml` — multi-page nav (About · Research ·
   Publications · Talks · Experience · CV).
3. `layouts/_partials/hooks/head-end/custom-styles.html` — small `<style>`
   block: 760 px column cap, NU purple links, neutralised gradient /
   shadow / rounded-box decoration, tightened heading scale. Hugo's
   hook system auto-injects everything in this directory before
   `</head>`.

Three reference sites motivated this look: `hrzhang.me` (al-folio),
`jenfowlie.com` (Google Sites), `sites.northwestern.edu/bartongroup/`
(NU WordPress). Keep edits compatible with that aesthetic: no card
grids, no gradient hero, no CTA cards, sans-serif, narrow column,
content does the work.

## Asset conventions

- CV PDF lives at `static/uploads/cv.pdf` and is served from `/uploads/cv.pdf`.
  The "Download CV" button on the homepage and the `CV` nav link both point
  there. Re-upload the file when the CV is updated.
- Per-page hero / featured images: drop `featured.jpg` (or `.png`) into
  the same folder as the `index.md`. Optional — pages without an image
  render fine.

## Deployment notes

The site is set up to publish to GitHub Pages (per Sunny's original
plan). `baseURL` in `config/_default/hugo.yaml` is currently a
placeholder (`https://ldyuan.github.io/`) — update it once the
actual repo / domain is known. A `.github/workflows/` directory exists
from the starter; review the workflow file before pushing.

## Things to remember when editing

- **Author folder vs author data file.** `content/authors/_index.md` has
  `build.render: never` cascaded over the whole directory. Do *not*
  create `content/authors/me/_index.md` — author data lives in
  `data/authors/me.yaml` instead.
- **Featured pubs vs all pubs.** The homepage *Featured Publications*
  block filters on `featured: true`. The *All Publications* block lists
  everything in `content/publications/`. Don't try to control order with
  a `weight` field — sort by `date`.
- **Preprints.** Use `publication_types: ["manuscript"]` in the
  frontmatter. They render in the citation list like everything else.
- **Tailwind v4 requires the CLI on PATH at build time.** This is the
  single most common cause of red-text errors here.
