# Zehui Guo — Personal Website

This repository contains the source for [https://zehguo.github.io](https://zehguo.github.io), a personal website presenting my research background, publications, and CV.

The site is built with Jekyll and is based on the [Academic Pages](https://github.com/academicpages/academicpages.github.io) template.

## Content map

The main content can be updated without changing the theme code:

- `_pages/about.md` — home page
- `_pages/research.md` — research overview
- `_pages/cv.md` — web CV
- `_pages/publications.html` — publication-list layout
- `_publications/` — one Markdown file per publication
- `_config.yml` — site title, description, author details, and public profile links
- `_data/navigation.yml` — top navigation

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

Use `category: manuscripts` for journal articles and `category: conferences` for conference papers.

## Preview locally

Ruby and Bundler are required. From the repository directory:

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
