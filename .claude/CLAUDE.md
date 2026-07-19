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
- `docs/kb/` — career knowledge base (see "Knowledge base" section below)
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

## Knowledge base
- `docs/kb/` is the **source of truth** for career content: `README.md` (core facts, locked decisions, writing rules), `dev-knowledge.md` (jobs track), `research-knowledge.md` (PhD/research track). When updating the CVs or `_pages/` content, pull facts, bullets, and citations from here; when real-world facts change, update the KB first, then propagate downstream.
- The KB is **committed to this public repo** but excluded from the Jekyll build (`docs` in `_config.yml` exclude), so it is visible on GitHub without being rendered on the site.
- **Sanitization rules** (in `docs/kb/README.md`) apply to everything under `docs/`: no phone number, no NDA-covered or client-confidential specifics, no private-repo file paths, no compensation or interview-strategy notes. That material lives only in the private layer at `~/Documents/personal-notes/career-kb.md` (local, never committed).

## Out of repo
- `~/Documents/personal-notes/career-kb.md` — the private layer of the knowledge base (see above). Deprecated as the general KB; still holds what may not be public.
- CV markdown page (`_pages/cv.md`) is hand-maintained separately from the LaTeX source and the PDFs; keep it in sync manually.

## Commit style
Short imperative present tense, lowercase (e.g., `update cv`, `update skills`, `update jexp`). Match the existing log.
