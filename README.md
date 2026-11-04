# chandravardhan-singh-raghaw.github.io

Personal academic website, built on the [AcademicPages](https://github.com/academicpages/academicpages.github.io) Jekyll template.

## Deploy on GitHub Pages (one-time)

1. Create the repository `chandravardhan-singh-raghaw.github.io` on GitHub (or open it if it exists).
2. Copy **everything** in this folder, including the hidden `.github` and `.gitignore`, into the repository root and push to `main` (or `master`).
3. GitHub → **Settings → Pages → Build and deployment → Source: GitHub Actions**.
   This is important: the template needs Jekyll 4, which GitHub's classic "Deploy from a branch" builder does not support. The workflow in `.github/workflows/jekyll.yml` builds and publishes the site on every push.
4. Watch the **Actions** tab; after a green run the site is live at <https://chandravardhan-singh-raghaw.github.io/>. Builds take 1–2 minutes.

## Where things live

| What | File(s) |
|---|---|
| Name, email, links in the sidebar | `_config.yml` → `author:` block |
| Menu | `_data/navigation.yml` |
| Home page (about, news, selected papers) | `_pages/about.md` |
| CV | `_pages/cv.md`; PDF at `files/CV_Chandravardhan_Singh_Raghaw.pdf` |
| Publications | one Markdown file per paper in `_publications/` |
| Teaching | one file per institution in `_teaching/` |
| Gallery | `_pages/gallery.md` (photo lists in the front matter) + images in `images/gallery/` |
| Profile photo | `images/profile.png` |
| Footer (last updated, visit counter) | `_includes/footer.html` |
| Extra CSS | `_sass/layout/_custom.scss` |

## Adding a publication

Create `_publications/YYYY-MM-DD-short-title.md`:

```yaml
---
title: 'Paper title'
collection: publications
category: manuscripts        # conferences | manuscripts | chapters | preprints | underreview
permalink: /publication/YYYY-MM-DD-short-title
date: YYYY-MM-DD
venue: 'Journal or conference name'
citation: '<b>Chandravardhan Singh Raghaw</b>, Co Author, and Last Author. &quot;Paper title.&quot; <i>Venue</i>, vol. 1, 2027.'
badges: 'First author · IF 7.5 · Q1'   # optional, separated by " · "
paperurl: 'https://doi.org/10.xxxx/yyyy'  # optional; the title links here
---
```

Move a paper from `underreview` to its final category when it is accepted, and update `date`.

## Adding a photo

Drop the image into `images/gallery/`, then add an entry to the relevant list in the front matter of `_pages/gallery.md`:

```yaml
  - url: gallery/emnlp-2026.jpg
    image_path: gallery/emnlp-2026.jpg
    alt: "Presenting at EMNLP 2026"
    title: "Presenting CliQ-RRG at EMNLP 2026"
```

## Visit counter and "last updated"

* **Last updated** is the build time, so it changes automatically with every push.
* **Visits** uses the free [CounterAPI](https://counterapi.dev) service (namespace and key are set in `_includes/footer.html`). A visit is counted once per browser session, so refreshing or moving between pages does not add to the count. If the service is unreachable the counter hides itself. To switch to another service (e.g. GoatCounter, which also gives you a private analytics dashboard) replace the `<script>` block in `_includes/footer.html`.

## Previewing locally (optional)

With Docker installed: `docker compose up` then open <http://localhost:4000>. Or with Ruby: `bundle install && bundle exec jekyll serve`.
