# Zehui Guo — Personal Website

This repository contains the source for [https://zehguo.github.io](https://zehguo.github.io), a personal website presenting my research background, publications, and CV.

The site is built with Jekyll and is based on the [Academic Pages](https://github.com/academicpages/academicpages.github.io) template.

## Content map

The main content can be updated without changing the theme code:

| Page | English | Japanese | Chinese |
| --- | --- | --- | --- |
| Home | `_pages/about.md` (`/`) | `_pages/ja/about.md` (`/ja/`) | `_pages/zh/about.md` (`/zh/`) |
| Research | `_pages/research.md` | `_pages/ja/research.md` | `_pages/zh/research.md` |
| Publications | `_pages/publications.html` | `_pages/ja/publications.html` | `_pages/zh/publications.html` |
| CV | `_pages/cv.md` | `_pages/ja/cv.md` | `_pages/zh/cv.md` |

Shared files:

- `_publications/` — one Markdown file per publication, shared by all three languages
- `_includes/publication-list.html` — the publication list used by every publication page
- `_config.yml` — site title, description, author details, and public profile links
- `_data/navigation.yml` — header links for each language
- `_data/i18n.yml` — interface text for each language (sidebar name and bio, labels, publication headings)

Publication records use front matter such as:

```yaml
title: "Paper title"
authors: "<strong>Z. Guo</strong> and Coauthor"
collection: publications
category: conferences
permalink: /publication/short-name
date: 2026-01-01
venue: "Conference or Journal"
paperurl: "https://doi.org/..."
citation: "Full citation"
```

Use `category: manuscripts` for journal articles and `category: conferences` for conference papers. Use the title exactly as published, and keep it consistent with the CVs.

## Languages

English pages live at the site root, Japanese pages under `/ja/`, and Chinese pages under `/zh/`. Each translated page sets two front-matter fields:

```yaml
lang: ja        # en (default when omitted), ja, or zh
ref: research   # the same value on every translation of this page
```

`ref` connects the translations: the language switcher in the header links to the page with the same `ref` in the other language, and the `<head>` gets matching `hreflang` links for search engines. A page without a translation is fine; the switcher then links to that language's home page. Publication detail pages stay in English because the papers are in English.

When changing a fact (a date, a title, a result), change all three languages in the same commit and keep the same strength of claim in each. The current CVs are the reference for dates and titles.

## Adding content later

- **Files (CV PDF, slides, posters):** put them in `files/` and link to them as `/files/name.pdf`. A publication can link slides with `slidesurl: /files/name.pdf` in its front matter.
- **A new section (for example Talks or Projects):** create the page in each language with matching `ref`, then add one entry per language to `_data/navigation.yml`.
- **A collection of entries (for example one file per talk):** add it under `collections:` in `_config.yml`, create the folder (`_talks/`), and list the entries from the section page. The theme already provides `_layouts/talk.html` and `_includes/archive-single-talk.html` for talks.
- **A new interface string:** add the same key to every language in `_data/i18n.yml`.

## Preview locally

Ruby 3.x and Bundler are required (the Ruby that ships with macOS is too old). From the repository directory:

```bash
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve
```

Then open [http://localhost:4000](http://localhost:4000). Restart the server after changing `_config.yml`.

Docker can be used instead if it is installed:

```bash
docker compose up --build
```

## Publish through GitHub Pages

The public site is generated from the GitHub repository `ZehGuo/ZehGuo.github.io`.

1. Review the changed files locally.
2. Commit the changes.
3. Push the `master` branch to GitHub.
4. Open the repository on GitHub and check **Actions** for the Pages build.
5. After the build succeeds, verify the live site at [https://zehguo.github.io](https://zehguo.github.io).

If publishing is not enabled, open **Settings → Pages** and select deployment from the repository's `master` branch and root directory.

## Privacy

Only information intended for public display should be copied into this repository. Do not add private CVs, identification documents, phone numbers, home addresses, student IDs, certificates, or personal photographs without reviewing them first.

The contact email and external profiles in `_config.yml` are public when the site is published.

## Theme attribution

The site uses [Academic Pages](https://github.com/academicpages/academicpages.github.io), which is based on the [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) Jekyll theme. See `LICENSE` for license information.
