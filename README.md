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
| Experience → Teaching tab | one file per institution in `_teaching/` |
| Experience → Industrial tab | `_data/industrial.yml` |
| Selected-publication slider (home) | `_data/selected.yml` + figures in `images/pubs/` |
| Academic service | `_pages/academic-service.md` |
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

## Selected-publication slider (home page)

Each slide is an entry in `_data/selected.yml`. Replace the placeholder figures in `images/pubs/` with your graphical abstracts (16:9, about 1200×675 px, PNG or JPG) and update the `image:` field to the new file name. The slider advances every 6 seconds, pauses on hover, and supports arrows, dots, keyboard and swipe.

## Visitor counter and "last updated"

* **Last updated** (footer) is the build time, so it changes automatically with every push.
* **Unique visitors** (bottom-right pill) uses [GoatCounter](https://www.goatcounter.com) — free for personal sites, no ads, no cookies, and it gives you a private dashboard. It is wired so that a visitor is counted **once per browser session**: refreshing, or opening other pages of the site, never adds to the count. The pill stays hidden until you finish this one-time setup:
  1. Go to <https://www.goatcounter.com/signup>, create an account and choose a **code** — e.g. `chandravardhan`. Your dashboard will be at `chandravardhan.goatcounter.com`.
  2. In that dashboard open **Settings → Visitor counter** (sometimes under *Settings → Main → Visitor counter*) and tick **"Allow adding visitor counts on your website"**, then Save.
  3. In `_config.yml` set `goatcounter_code: "chandravardhan"` (your code), commit and push.
  After the next build the pill shows the total; the first number you see will be 1 (you).

## Sidebar links

In `_config.yml` → `author:` fill in `semantic:` (Semantic Scholar author page URL) and `dblp:` (DBLP page URL) and they appear in the sidebar and on the Publications page. The email is shown as `name [at] domain` and the mailto link is assembled only when clicked, to reduce scraping.

## Previewing locally (optional)

With Docker installed: `docker compose up` then open <http://localhost:4000>. Or with Ruby: `bundle install && bundle exec jekyll serve`.
