# guidoardizzone.github.io

Personal academic website for Guido Ardizzone. Static HTML + CSS, no build step.
Served by GitHub Pages from the `main` branch, root directory.

## Local preview

No server strictly required — open `index.html` in a browser. To test relative
paths exactly as GitHub Pages serves them:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Structure

```
index.html            Home
research.html         Research
cv.html               Vitae (short summary; full PDF in files/cv.pdf)
teaching-writing.html Teaching & Writing (teaching + Tortuga articles)
styles.css        Single shared stylesheet
assets/           Photo and other images
files/            Self-hosted PDFs (cv.pdf, paper drafts)
robots.txt
sitemap.xml
```

The header nav is a copy-pasted block inside each HTML file (search for
`SHARED NAV`). There is no template engine — if you change a nav link, change it
in all four files.

## How to add a new paper

Open `research.html` and copy an existing `<article class="paper">` block into
the right section (`Job Market Paper`, `Working Papers`, or `Work in Progress`).
Fill in:

```html
<article class="paper">
  <p class="title">Paper Title Here</p>
  <p class="meta">with Coauthor Name (Affiliation) · Status or venue</p>

  <!-- Link a coauthor to their site: -->
  <!-- with <a href="https://...">Coauthor Name</a> -->

  <!-- Link the title only if a PDF exists: -->
  <!-- <p class="title"><a href="files/paper.pdf">Paper Title Here</a></p> -->

  <!-- Optional abstract, collapsed by default: -->
  <details class="abstract">
    <summary>Abstract</summary>
    <p>Abstract text here.</p>
  </details>

  <!-- Optional external coverage: -->
  <!-- <p class="coverage">[<a href="https://...">VoxEU</a>]</p> -->
</article>
```

Rules of thumb:

- **No PDF, no title link.** Only the job market paper carries a `Draft in progress` tag.
- **Self-host PDFs** under `files/`. No Google Drive / Dropbox / GitHub blob links.
- **Don't invent abstracts.** Omit the `<details>` block if there's no real text.

## How to add a policy article

Open `teaching-writing.html` and add a `<dt>`/`<dd>` pair at the top of the
Policy Writing list (newest first): date, linked title (`lang="it"` for Italian
titles), then the outlet in `<em>`.

## Updating the CV

The full CV PDF is built from `files/cv.tex`, a copy of
`2_University/1-Job Hunt/1_Resources/1.CV/main_research.tex`. Edit the source there, copy it over, run
`pdflatex cv.tex` in `files/`, and keep `cv.html` in step by hand.

## Adding the headshot

Drop a photo at `assets/headshot.jpg` and change the `src` in `index.html` from
`assets/photo-placeholder.svg` to `assets/headshot.jpg`.

## Updating the sitemap

If you add a page, add its `<loc>` to `sitemap.xml`.
