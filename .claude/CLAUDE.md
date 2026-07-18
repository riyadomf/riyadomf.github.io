# Repo: riyadomf.github.io

Personal academic/portfolio site for **Md Omar Faruqe (Riyad)**. Built on the [academicpages](https://academicpages.github.io/) Jekyll template, deployed via GitHub Pages at https://riyadomf.github.io.

## Stack
- **Jekyll** (Ruby) + GitHub Pages
- Theme: academicpages (Minimal Mistakes fork)
- Site config: `_config.yml` (site-wide settings, author profile, social links, publication categories, collections)
- Navigation: `_data/navigation.yml`

## Directory map
- `_pages/` — top-level pages (about.md is the homepage; cv.md, skills.md, projects.md, job-experience.md, research-experience.md, certifications-achievements.md, publications.html, talks.html, teaching.html, portfolio.html)
- `_publications/` — one markdown file per publication (filename pattern: `YYYY-MM-DD-slug.md`)
- `_portfolio/` — portfolio items
- `_posts/` — blog posts (`YYYY-MM-DD-slug.md`)
- `_talks/`, `_teaching/` — collections rendered by template
- `_includes/`, `_layouts/`, `_sass/` — theme internals; only touch if changing presentation
- `_data/` — `authors.yml`, `navigation.yml`, `ui-text.yml`
- `files/` — static downloads (CV PDFs live here as `CV-Md_Omar_Faruqe*.pdf`, plus `certifications/` and `slides/`)
- `images/` — site images (author avatar referenced from `_config.yml` is `omar-dp.png`)
- `assets/` — compiled CSS/JS from theme
- `markdown_generator/` — optional TSV→markdown scripts for publications/talks (Jupyter)
- `resume/` — LaTeX CV sources (kept here so portfolio + CV live in one repo). Two variants: `Omar_research_cv/main.tex` (academia) and `Omar_Dev_cv/main.tex` (industry/developer). Whichever is currently in use gets compiled locally and its PDF dropped into `files/` as `CV-Md_Omar_Faruqe*.pdf` for the portfolio download. Excluded from the Jekyll build via `_config.yml` so the raw `.tex` is not published.
- `_site/`, `vendor/` — build output and bundler cache (do not edit)

## Local dev
```bash
bundle install         # first time
jekyll serve -l -H localhost   # http://localhost:4000, live reload
```
Docker alternative: `docker build -t jekyll-site .` then run the container per README.

## Conventions for content edits
- Page front matter follows Jekyll YAML; preserve `permalink`, `layout`, `author_profile` fields when editing.
- New publication: drop a new file in `_publications/` matching the existing pattern; no index file to update.
- Author/contact info, social handles, SEO, analytics IDs all live in `_config.yml` — change there, not in pages.
- Adding to nav: edit `_data/navigation.yml`.
- Don't use em dashes (—) in page copy; they read as AI-generated. Use commas, periods, or parentheses instead.

## Out of repo
- CV LaTeX source now lives in `resume/` (see Directory map). The `files/CV-Md_Omar_Faruqe*.pdf` download is the compiled output of whichever variant is active.
- CV markdown page (`_pages/cv.md`) is hand-maintained separately from the LaTeX source and the PDFs; keep it in sync manually.

## Commit style
Short imperative present tense, lowercase (e.g., `update cv`, `update skills`, `update jexp`). Match the existing log.
