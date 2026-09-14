# Portfolio site

Hugo + PaperMod. Same setup Dr. Beal's lab site uses.

## Run it locally

1. Install Hugo (extended). You need **0.146 or newer** for this theme.
   - Windows: `winget install Hugo.Hugo.Extended`
   - macOS: `brew install hugo`
   - Linux: download from https://github.com/gohugoio/hugo/releases
2. In this folder, run: `hugo server`
3. Open http://localhost:1313

The site rebuilds and the browser refreshes every time you save a file.

## What to edit

| What you want to change | File |
|---|---|
| Your name, role, blurb, photo, social links | `hugo.yaml` |
| The tabs across the top | `hugo.yaml`, the `menu:` section |
| Research focus cards and News feed on the home page | `content/_index.md` |
| Research statement and current work | `content/research.md` |
| Publications, preprints, posters | `content/publications.md` |
| CV summary page | `content/cv.md` |
| About page | `content/about.md` |
| A project write-up | `content/projects/*.md` |
| A note or blog post | `content/notes/*.md` |
| Photos, resume PDF, favicon | `static/` |

## Add a project

Make a new file in `content/projects/`, for example `bms.md`:

```markdown
---
title: "6S Battery Management System"
date: 2026-02-10
summary: "Passive balancing, coulomb counting, and a hardware fault latch."
tags: ["battery", "safety"]
cover:
  image: "/images/bms.jpg"
  alt: "BMS board"
  relative: false
math: true
---

Your write-up here. Regular Markdown.
```

Then drop `bms.jpg` into `static/images/`. That's it — it shows up on the
Projects page automatically, newest first.

## Math

Put `math: true` in a page's front matter and you can write LaTeX:
`$$ D = \frac{V_{out}}{V_{in}} $$`

Without that flag the page skips loading KaTeX, so it stays fast.

## Files you need to add

- `static/images/headshot.jpg` — your photo (square, ~500x500)
- `static/cv.pdf` — your CV
- `static/images/*.jpg` — one photo per project
- `static/favicon.ico` — optional

## Deploy

**Vercel** (what Dr. Beal uses): push this folder to GitHub, then import the
repo at vercel.com. It detects Hugo automatically. `vercel.json` already pins
the Hugo version so the build won't fail on an old default.

**Netlify:** same, but set build command `hugo --gc --minify`, publish
directory `public`, and environment variable `HUGO_VERSION` = `0.151.0`.

Set `baseURL` in `hugo.yaml` to your real URL after the first deploy.
