# The Quiet Signal — Jekyll blog

A responsive, dark editorial-style blog built with Jekyll and designed for GitHub Pages. It includes a homepage, featured latest post, archive, topic index, about page, custom post/page layouts, RSS, SEO metadata, a 404 page, and a custom stylesheet.

## 1. Customize the site

Edit `_config.yml`:
- `title` and `description`
- `url` — your GitHub Pages URL, such as `https://yourname.github.io`
- `baseurl` — leave blank for a user/organization site; for a project site, set it to `/repository-name`
- `author.name`
- social links

Also update `robots.txt` with your real site URL. Replace the sample name and links in `about.md` and `_config.yml`.

## 2. Create your GitHub repository

For a personal site, create a repository named exactly `YOUR-USERNAME.github.io`.
For a project site, any repository name works.

Copy the contents of this folder into the repository, commit, and push to the `main` branch.

## 3. Enable GitHub Pages

In the repository, open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/(root)`, then save. GitHub will build the Jekyll site automatically.

If you use a custom domain, configure it under Settings → Pages and add the DNS records your domain provider requires.

## 4. Write a post

Create a Markdown file in `_posts` with the date-prefixed filename format:

`_posts/2026-10-27-a-first-note.md`

Use front matter at the top:

```yaml
---
layout: post
title: "A First Note"
date: 2026-10-27 09:00:00 -0600
categories: [journal]
tags: [notes, beginnings]
description: "A short description for search and sharing."
---

Your post begins here. Write in **Markdown**.
```

The filename date is important. Posts are sorted by date, newest first. Use lowercase filenames and hyphens.

## 5. Preview locally (optional)

Install Ruby and Bundler, then from this directory run:

```sh
bundle install
bundle exec jekyll serve
```

Open `http://127.0.0.1:4000`. If you use a project site with a `baseurl`, preview with that value configured.

## Included structure

```text
.
├── _config.yml
├── _layouts/
│   ├── default.html
│   ├── home.html
│   ├── page.html
│   └── post.html
├── _posts/
├── assets/css/style.css
├── about.md
├── archive.md
├── topics.md
├── index.html
├── 404.html
├── feed.xml
├── Gemfile
└── robots.txt
```

The visual theme uses CSS-only abstract artwork, so there are no external image assets to manage. Google Fonts are optional; the site has system-font fallbacks.
