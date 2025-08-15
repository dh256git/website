# Flow & Interaction Group — Website Maintainers’ Guide

> A practical manual for contributors to the FIG Jekyll site (GitHub Pages). This covers the content model, front‑matter templates, gotchas, and our build/deploy options.

---

## Table of contents
1. [Overview](#overview)
2. [Repository layout](#repository-layout)
3. [Site config & defaults](#site-config--defaults)
4. [Content types & how to add them](#content-types--how-to-add-them)
   - [Themes (`_themes`)](#themes-_themes)
   - [Publications (`_publications`)](#publications-_publications)
   - [People (data file)](#people-data-file)
   - [Posts (Blog items)](#posts-blog-items)
   - [Podcasts (`_podcasts`)](#podcasts-_podcasts)
   - [Videos (`_videos`)](#videos-_videos)
   - [Transcripts (`assets/transcripts/`)](#transcripts-assetstranscripts)
   - [Projects (`_projects`, optional)](#projects-_projects-optional)
5. [Cross‑linking model](#crosslinking-model)
6. [Layouts & includes](#layouts--includes)
7. [Styling & accessibility](#styling--accessibility)
8. [URLs, permalinks & baseurl](#urls-permalinks--baseurl)
9. [Build & deploy](#build--deploy)
   - [A. Build with GitHub Pages (no plugins)](#a-build-with-github-pages-no-plugins)
   - [B. Build with GitHub Actions (plugins enabled)](#b-build-with-github-actions-plugins-enabled)
10. [Maintenance checklists](#maintenance-checklists)
11. [Gotchas & tips](#gotchas--tips)
12. [Appendix: front‑matter templates](#appendix-frontmatter-templates)

---

## Overview

This site is a static Jekyll website deployed on GitHub Pages. We use simple, low‑maintenance content models for **Themes**, **Publications**, **People**, and **Media** (Posts, Podcasts, Videos), plus optional **Projects**. Everything is designed to work in GitHub Pages’ default environment; optional pagination and extra plugins are available when building with GitHub Actions.

---

## Repository layout

```
/
├─ _config.yml
├─ assets/
│  ├─ css/main.scss
│  ├─ img/
│  │  └─ people/<key>.jpg              # person images (square, ~96–512px)
│  └─ transcripts/                     # transcript pages (.md preferred)
├─ _data/
│  └─ people.yml
├─ _includes/
│  ├─ audio.html                       # accessible audio embed
│  ├─ pub-card.html                    # publication card
│  └─ youtube.html                     # privacy-enhanced YouTube embed
├─ _layouts/
│  ├─ default.html
│  ├─ post.html                        # blog post
│  ├─ publication.html                 # publication page
│  ├─ theme.html                       # research theme page
│  ├─ podcast.html                     # podcast item page
│  ├─ video.html                       # video item page
│  ├─ transcript.html                  # transcript page
│  └─ project.html                     # (optional) project page
├─ _publications/
├─ _themes/
├─ _podcasts/
├─ _videos/
├─ _projects/                          # optional
├─ _posts/                             # blog posts
└─ media/                              # media landing + (optional) paginated lists
```

---

## Site config & defaults

Key expectations set in `_config.yml` (names may vary slightly in your repo):

```yml
title: Flow & Interaction Group
timezone: Europe/London
permalink: pretty           # /path/ instead of /path.html
# baseurl: "/<repo>"        # only for project sites (not user/org sites)

collections:
  podcasts:
    output: true
    permalink: /media/podcasts/:title/
  videos:
    output: true
    permalink: /media/videos/:title/
  projects:
    output: true
    permalink: /projects/:title/

defaults:
  - scope: { path: "", type: "posts" }
    values: { layout: post }
  - scope: { path: "", type: "podcasts" }
    values: { layout: podcast }
  - scope: { path: "", type: "videos" }
    values: { layout: video }
  - scope: { path: "assets/transcripts" }
    values: { layout: transcript }   # makes transcript .md files auto-use this layout
```

- **No need to set `layout:`** on most items; defaults do it.
- **Permalinks** use `:title/` (or `:name/`) for clean URLs.

---

## Content types & how to add them

### Themes (`_themes`)
Themes define research areas and power **tag pills** + filtering.

**Front matter**
```md
---
title: Flow-Centred Design & Haptic Learning
slug: flow-centred-design-haptic-learning
description: One–two sentence summary of the theme.
---

(Optional longer description/notes.)
```

**Tag mapping**: When any content’s `tags` includes a theme’s `slug`, that item appears on the theme page and gets a pretty **tag pill** that links back to this theme.

---

### Publications (`_publications`)

**Must‑have fields**: stable `slug`, `title`, `authors`, `venue`, `year`. Links are optional but encouraged.

```md
---
title: "Benthic: Perceptually congruent structures for..."
slug: benthic
authors: A. Author; B. Author
venue: Proc. CHI
year: 2025
doi: 10.1145/xxxxxxx
publisher_url: https://doi.org/10.1145/xxxxxxx
pdf_url: /assets/papers/benthic.pdf
html_url: /assets/papers/benthic.html
tags: [representational-productivity-tools]
---

(Optional abstract in Markdown – shown on the page.)
```

- **Media linkage**: media items (posts/podcasts/videos) list related publications via `related_publications: [benthic, …]`. The publication page aggregates and shows them with emojis (📝/🎧/🎬).

---

### People (data file)

People live in `_data/people.yml`. Keys = short IDs (used for image filenames). Sections are **comments** only; the template groups by attributes.

Required keys per person:
- `name`, `url`, `title`, `affiliation`
- Optional: `alumni: true`, `next: ...`, `collaborators: true`, `alt:`

**Image rule**: drop a square image at `assets/img/people/<key>.jpg` — the card uses it automatically. If `alt` missing, we fallback to `Profile picture of <name>`.

Example:
```yml
hajas:
  name: Daniel Hajas
  url: https://profiles.ucl.ac.uk/87472-daniel-hajas
  title: Principal Investigator
  affiliation: University College London
  alt: ...

jzong:
  name: Jonathan Zong
  url: http://jonathanzong.com/
  title: Associate Professor
  affiliation: University of Colorado Boulder
  collaborators: true
```

---

### Posts (Blog items)

Posts render with `_layouts/post.html`. They support:
- **AI assistance indicator** (`AI_assistance`: `AI-assisted` / `AI-generated`; default is AI‑free)
- **Related publications** (cards will show)
- **Related external articles** (array of `{title, url}`)
- **Hero image** (with alt/caption & accessible fallback)

```md
---
title: Feeling Shapes in Mid-Air
date: 2025-08-14
tags: [representational-productivity-tools]
AI_assistance: AI-assisted
related_publications: [benthic]
related_external_posts:
  - title: "Press release: Mid-air haptics breakthrough"
    url: https://example.org/press
hero: /assets/img/posts/squeeze-hero.jpg
hero_alt: "Participant feeling a mid-air tactile square produced by ultrasound"
hero_caption: "Photo © Flow & Interaction Group"
---

Post body here…
```

**News posts**: If a post has the tag `news`, it appears on the homepage **News** section and is **excluded** from the Media “Blog posts” list.

---

### Podcasts (`_podcasts`)

```md
---
title: Drawing Tactile Shapes in Mid-Air
date: 2025-08-14
summary: Short blurb shown above the player.
audio_url: /assets/audio/episode.mp3        # or
embed_html: "<iframe ... allow='...'></iframe>"
transcript_url: /assets/transcripts/drawing-tactile-shapes-in-mid-air.html
related_publications: [benthic]
tags: [flow-centred-design-haptic-learning]
---

(Optional show notes – rendered after the player)
```

- If you provide `embed_html`, it’s used; else we fall back to native `<audio>`.
- The player include is `_includes/audio.html` (div-based, transcript link).

---

### Videos (`_videos`)

```md
---
title: Intro to FIG
date: 2025-08-13
summary: Lightning intro to our mission and themes.
youtube_id: dQw4w9WgXcQ      # privacy-enhanced player via include
youtube_title: "Intro to the Flow & Interaction Group"
# or embed_html: "<iframe ...>"
related_publications: [benthic]
tags: [cross-modal-ux-collaboration]
---

Transcript text can live directly in the file if you want, but we usually link to a transcript page.
```

- The layout prints **summary, then the embed**, matching our publication/theme media lists.
- YouTube iframe uses `youtube-nocookie.com` via `_includes/youtube.html`.

---

### Transcripts (`assets/transcripts/`)

Prefer **Markdown** files with `layout: transcript` and a **fixed permalink** if you want a `.html` URL:

```md
---
layout: transcript
permalink: /assets/transcripts/drawing-tactile-shapes-in-mid-air.html
title: "Drawing Tactile Shapes in Mid-Air (transcript)"
date: 2025-08-14
audio_length: "20:12"
recorded: "Aug 14, 2025 11:08 AM"
participants:
  - Speaker 1 (AI host 1)
  - Speaker 2 (AI host 2)
source_url: /media/podcasts/drawing-tactile-shapes-in-mid-air/
---

Transcript body…
```

> **Important:** If a transcript file has front matter, Jekyll treats it as a page. Either set a `.html` `permalink:` (as above) **or** link to the folder URL `/.../drawing-tactile-shapes-in-mid-air/` (pretty permalinks).

---

### Projects (`_projects`, optional)

```md
---
title: Mid-Air Dynamic Tactile Pointer
date: 2024-11-01
summary: Improves recognition of 2‑D shapes via brief pauses at corners.
external_url: https://example.org/tactile-pointer
tags: [flow-centred-design-haptic-learning, representational-productivity-tools]
---

Short project description…
```

Projects auto-appear on relevant **Theme** pages based on `tags`.

---

## Cross‑linking model

- **Themes**: add the theme’s `slug` to any content’s `tags` → that item appears on the theme page and gets a pretty tag pill that links back to the theme.
- **Publications ↔ Media**: media items declare `related_publications: [slug, …]`. Publication pages auto-aggregate **Blog posts (📝), Podcasts (🎧), Videos (🎬)** and embed players for podcasts/videos.
- **Transcripts ↔ Media**: transcripts can set `source_url:` to link back to the originating podcast/video page.

---

## Layouts & includes

**Layouts**
- `default.html` — global wrapper (header/nav/footer).
- `post.html` — blog post; shows date/author, AI indicator (✍️/🤝/🤖), hero image, related publications (cards), related external links, tag pills (pretty theme titles).
- `publication.html` — details + Abstract + unified Media list (📝/🎧/🎬; summary before embed).
- `theme.html` — description, Projects, Publications (as `pub-card`), and unified Media list (same as publication page).
- `podcast.html` — title → meta → summary → audio embed (+ optional notes).
- `video.html` — title → meta → summary → YouTube embed → **Transcript** heading, then body.
- `transcript.html` — title → meta (date, duration, recorded, participants, optional summary) → transcript body.
- `project.html` — title → meta (date, external link) → summary → body.

**Includes**
- `pub-card.html` — consistent publication listing with links.
- `youtube.html` — privacy-enhanced embed.
- `audio.html` — accessible audio; uses native `<audio>` or host iframe; transcript link.

---

## Styling & accessibility

- **People cards** enforce square images via `object-fit: cover` and fixed container (96×96 on desktop, 72×72 on small screens).
- **Tag pills** show the theme’s **pretty title** and link to the theme page (fallback to raw tag if no theme exists).
- **External links**: `target="_blank" rel="noopener"` + `aria-label="… (opens in a new tab)"`.
- **Hero images**: provide `hero_alt` when informative. If absent but a caption exists, the figure uses `aria-labelledby` so the caption becomes the accessible name.
- **Embeds**: YouTube uses `youtube-nocookie.com`; audio provides a **Transcript** link; both are placed **after** summaries in media lists for podcasts/videos.
- **ARIA**: we avoid redundant region labels; headings provide structure.

---

## URLs, permalinks & baseurl

- **Pretty permalinks** are enabled. Pages with front matter will output to `/path/` unless you set an explicit `.html` `permalink`.
- If the site is a **project site** (`username.github.io/repo`), set `baseurl: "/repo"` in `_config.yml`, and always pipe links through `| relative_url` (already done in templates).
- **Transcripts**: If they have front matter, either link to the folder URL or set `permalink:` to the `.html` path you intend to link to from media players.

---

## Build & deploy

### A. Build with GitHub Pages (no plugins)
- GitHub builds directly from the branch (usually `main`).
- Use **no-plugin** features only (current site is compliant).
- Manual pagination (if desired) can be done with pre-made `/media/page/N/` pages (we provide an include for this).

### B. Build with GitHub Actions (plugins enabled)
- Switch **Settings → Pages → Build and deployment → Source → GitHub Actions**.
- Use the provided workflow to `bundle install` and `jekyll build`.
- Add plugins (e.g., `jekyll-paginate-v2`, `jekyll-seo-tag`) in `Gemfile` and `_config.yml`.
- Create paginated indexes for:
  - `/media/blog/` (posts excluding `news`)
  - `/media/podcasts/` (podcasts collection)
  - `/media/videos/` (videos collection)

See `.github/workflows/pages-jekyll.yml` in this repo for a working example.

---

## Maintenance checklists

**Before publishing**
- [ ] All publication slugs set; theme slugs correct.
- [ ] People images present and not oversized.
- [ ] External links use `rel="noopener"` and `aria-label` for “opens in a new tab”.
- [ ] Transcripts: `permalink` set (or we link to folder URL), `source_url` points to canonical media page.
- [ ] Media hub shows latest items; paginated lists work (if Actions build).

**When adding new content**
- **Posts**: set `AI_assistance` if applicable; add `related_publications`; add hero image if desired.
- **Podcasts/Videos**: add `summary`; prefer `embed_html` if host provides; otherwise `audio_url` / `youtube_id`.
- **Transcripts**: set `audio_length`, `recorded`, `participants`, optional `source_url`.
- **Publications**: set `slug`, link fields, and `tags` to themes.
- **Projects**: add `summary` and optional `external_url`; tag with relevant theme slugs.

---

## Gotchas & tips

- **Colons in YAML**: quote titles like `"Benthic: …"` or Liquid parsing can break.
- **Slugs**: keep lowercase, hyphenated, no spaces. Avoid colons/Unicode punctuation.
- **Theme tag pills**: only theme slugs get pretty pills; other tags (e.g., `news`) render as plain pills.
- **Transcript 404s**: if a transcript has front matter, it’s a page. Either set a `.html` `permalink` (recommended) or link to the folder URL.
- **Figure vs. div**: our audio include uses a `<div class="audio-player">` to avoid extra landmarks/chatter.
- **Screen-reader helpers**: we use `aria-label` on “opens in a new tab” links; `.sr-only` utility exists if needed.
- **Local dev**: `bundle exec jekyll serve` (Ruby 3+ needs `webrick` gem).

---

## Appendix: front‑matter templates

**Post**
```md
---
title: "..."
date: 2025-08-14
author: "Name"
tags: [flow-centred-design-haptic-learning]
AI_assistance: AI-assisted        # AI-assisted | AI-generated (omit = AI-free)
related_publications: [benthic]
related_external_posts:
  - title: "Press release"
    url: "https://example.org/press"
hero: /assets/img/posts/example.jpg
hero_alt: "Descriptive alt"
hero_caption: "Photo © FIG"
---
```

**Publication**
```md
---
title: "Paper title"
slug: my-paper
authors: A; B; C
venue: Conference XYZ
year: 2025
doi: 10.xxxx/xxxx
publisher_url: https://doi.org/10.xxxx/xxxx
pdf_url: /assets/papers/my-paper.pdf
html_url: /assets/papers/my-paper.html
tags: [representational-productivity-tools]
---
Abstract…
```

**Podcast**
```md
---
title: "Episode title"
date: 2025-08-14
summary: "One-liner."
audio_url: /assets/audio/ep01.mp3   # or embed_html: "<iframe ...></iframe>"
transcript_url: /assets/transcripts/ep01.html
related_publications: [my-paper]
tags: [flow-centred-design-haptic-learning]
---
(Optional show notes)
```

**Video**
```md
---
title: "Video title"
date: 2025-08-14
summary: "One-liner."
youtube_id: dQw4w9WgXcQ             # or embed_html: "<iframe ...></iframe>"
related_publications: [my-paper]
tags: [cross-modal-ux-collaboration]
---
(Body used for transcript if desired)
```

**Transcript**
```md
---
layout: transcript
permalink: /assets/transcripts/ep01.html
title: "Episode 1 (transcript)"
date: 2025-08-14
audio_length: "20:12"
recorded: "Aug 14, 2025 11:08 AM"
participants:
  - Host
  - Guest
source_url: /media/podcasts/episode-1/
---
Transcript body…
```

**Project (optional)**
```md
---
title: "Project title"
date: 2025-01-10
summary: "One-liner."
external_url: https://example.org/project
tags: [representational-productivity-tools]
---
Body…
```

---

**Questions or improvements?** Open a PR with your change and a one‑line note in the commit message explaining the intent (content vs. layout vs. styling).

