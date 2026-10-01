# ma-2a.github.io

Source of [ma-2a.github.io](https://ma-2a.github.io): Home Assistant panels, 3D-printed parts, and small hardware builds, with the write-ups to go with them.

Built with Jekyll on GitHub Pages, using only `jekyll-feed`, `jekyll-seo-tag` and `jekyll-sitemap`.

The site and its texts are made with AI assistance.

## Writing a post

Add a file to `_posts/` named `YYYY-MM-DD-slug.md`:

```yaml
---
title:
description:      # one sentence, used for SEO and cards
category:         # one of: home-assistant, smart-home-for-everyone, 3d-printing, builds
tags: []
project:          # optional, e.g. panelkit
image:            # optional, /assets/img/posts/<slug>/cover.jpg
---
```

The post appears at `/blog/<slug>/`. Categories live in `_data/categories.yml`, projects in `_data/projects.yml`.

## Previewing locally

```
bundle exec jekyll serve
```

or any Jekyll 3.10 setup matching the GitHub Pages versions.
