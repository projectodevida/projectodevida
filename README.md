# PDV Theme — Setup Guide

## File structure

```
your-project/
├── hugo.toml
├── data/
│   └── changelog.yaml
├── layouts/
│   └── index.html
├── content/
│   ├── _index.md                ← homepage intro text
│   ├── blog/
│   │   ├── _index.md
│   │   └── notes-on-improvisation.md
│   ├── projects/
│   │   ├── _index.md
│   │   └── pdv004.md
│   ├── resources/
│   │   └── resources.md
│   └── contact/
│       └── _index.md
└── themes/
    └── pdv/
        ├── theme.toml
        ├── static/css/style.css
        └── layouts/
            ├── _default/
            │   ├── baseof.html
            │   ├── single.html
            │   └── list.html
            ├── partials/
            │   ├── head.html
            │   ├── header.html
            │   └── footer.html
            ├── projects/
            │   ├── single.html
            │   └── list.html
            └── resources/
                └── single.html
```


## Running locally in VSCode

1. Open your project folder in VSCode (File → Open Folder)
2. Open the integrated terminal (Terminal → New Terminal)
3. Check Hugo is installed:
   hugo version
   If not — Mac: brew install hugo / Windows: choco install hugo-extended
4. Start the local server:
   hugo server
5. Open http://localhost:1313 in your browser

The site hot-reloads on save. To include draft posts: hugo server -D


## Bilingual content

The `lang` field in front matter controls the tag shown on list pages.
Use `pt`, `en`, or `pt/en`. No routing or parallel folders involved —
it is purely a label.

### Blog post (single language)

---
title: "Notes on free improvisation"
date: 2025-01-18
lang: "en"
---
Text here.

### Blog post (bilingual, PT first)

---
title: "PDV003 — liner notes"
date: 2024-11-20
lang: "pt/en"
---
Texto em português aqui.

---
*english version below*
---

English text here.

### Project page

---
title: "Polido — Free Music II"
date: 2025-02-18
lang: "pt/en"
catalogue: "PDV004"
format: "CD-r"
year: 2025
duration: "50min."
price: "€5 + shipping"
files: "with purchase"
---
Description here. PT first, then divider, then EN.

### Changelog

Edit data/changelog.yaml, newest entry at top:

- date: "2025-03-01"
  note: "added PDV004 page"


## Deploying to GitHub Pages

Run: hugo
This builds into a public/ folder. Commit and push.
