# Personal academic website — build spec

## Role

You are building a personal academic website for **Guido Stefano Ardizzone**, a PhD
candidate in Economics at the Geneva Graduate Institute (IHEID). The audience is
seminar organisers, potential coauthors, policy researchers, and eventually hiring
committees. Assume a reader spends under 60 seconds on the site.

He is **not yet on the job market** (PhD started Sep 2022). This site is being built
early, so it should read as a researcher's professional home page, not as a job market
page. Do not add "on the 2026/27 job market" language or an oversized job-market-paper
banner. The JMP is labelled as such but sits in a normal paper list.

**Do not invent content.** Every title, name, date, and affiliation below is factual.
Where something is missing, either ask me (see "Interactive steps") or leave a visible
`TODO` in the page. Never write a plausible-sounding abstract, award, or affiliation
that is not in this document.

---

## 1. Interactive steps

Stop and ask me for these during the build rather than guessing. Ask for them one at a
time, in this order, and paste my answers verbatim into the HTML:

1. **Abstracts.** Ask me for the abstract of each paper, one paper at a time, in the
   order they appear in section 3. If I say "skip" for one, render the entry without an
   abstract block rather than inventing one.
2. **Headshot.** Ask me to drop a photo at `assets/photo.jpg`. If I haven't supplied
   one by the end of the build, use a neutral placeholder and tell me it's outstanding.
3. **Google Scholar URL.** I may not have a profile yet. If I don't, omit the link
   entirely rather than linking to a search page.
4. **CV.** You can locate my CV source on this machine yourself. Do **not** copy the
   existing PDF into `files/` as-is. Build a web-safe version first (see section 5),
   show me what you stripped, and only then publish it as `files/cv.pdf`.

## 2. Tech constraints

- Static HTML + CSS. **No build step, no framework, no npm, no Jekyll, no Ruby.**
  The site must work by opening `index.html` in a browser and by pushing to GitHub
  Pages with zero configuration.
- Repo: `guidoardizzone.github.io` (see the username note in section 5), `main` branch,
  served from root.
- No JavaScript except where genuinely unavoidable. Use native `<details>`/`<summary>`
  for collapsible abstracts, never a JS toggle. The site must be fully readable with JS
  disabled.
- No external font CDN, no Google Fonts, no analytics, no cookie banner. Self-host any
  webfont under `assets/fonts/` or use a system font stack.
- All PDFs self-hosted under `files/`. No Google Drive, Dropbox, or GitHub blob URLs.
- Add `robots.txt` and a minimal `sitemap.xml`. Skip `CNAME` unless I supply a domain.

## 3. Page structure

Four pages, shared header nav. Keep the nav as one copy-pasted block; four pages of
duplicated markup is cheaper to maintain than a toolchain.

```
index.html        Home
research.html     Research
teaching.html     Teaching
cv.html           CV
```

### Home (index.html)

Above the fold, in this order:

1. **Guido Ardizzone**
2. PhD Candidate in Economics, Geneva Graduate Institute (IHEID)
3. Photo at `assets/photo.jpg`
4. Research statement (draft below — show it to me for approval before using)
5. Email: `guido.ardizzone@graduateinstitute.ch`
6. Links: [LinkedIn](https://www.linkedin.com/in/guido-ardizzone-b52048174/),
   Google Scholar (ask first), IHEID profile page (ask me for the URL)
7. Link to CV PDF

Draft research statement:

> I am a PhD candidate in Economics at the Geneva Graduate Institute, supervised by
> Ugo Panizza. My research is in sovereign debt, macro-finance, and banking. I use
> granular credit registry and sovereign bond data to study how sovereign risk
> transmits to bank lending and firm outcomes, and how the seniority structure of
> sovereign debt shapes market access. I also work on the effects of financial
> sanctions on bank lending.

Below the fold, a short dated news list, most recent first, three to five items. Seed
with:

- Jun–Aug 2026 — Fund Internship Program, International Monetary Fund, Washington DC
- 2026 — Awarded the Gallatin Excellence Scholarship for a semester at a U.S. university
- Jul–Aug 2025 — Visiting PhD Student, The World Bank Group

**Do not list anything unconfirmed.** No pending applications, no prospective visits,
no programmes not yet accepted to.

### Research (research.html)

Three sections in this order: **Job Market Paper**, **Working Papers**, **Work in
Progress**. No "Publications" section — there are none yet, and an empty one draws
attention to the gap.

Entry format for each paper:

- Title in bold. Hyperlink it only if a PDF or working paper page exists; otherwise
  plain text with a status line reading "Draft in progress".
- Coauthors, each linked to their own site where a URL is supplied.
- Status line: series number, venue, or presentation history.
- Abstract inside a `<details>` element, collapsed, `<summary>` reading "Abstract".
- External coverage, if any, as small bracketed links under the title.

Content:

**Job Market Paper**
- *Sovereign Risk, Debt Maturity, and Firm Outcomes*
- Single-authored
- Status: Draft in progress. **No PDF link** — no circulatable draft exists yet.
- Abstract: ask me (interactive step 1)

**Working Papers**
- *Senior Debt and Market Access*, with
  [Agustín Velasquez](TODO: ask me for URL) and
  [Mahamoud Islam](TODO: ask me for URL), both IMF.
- Status: Presented at the IMF Fund Internship Program conference, 2026.
- Abstract: ask me

**Work in Progress**
- *Sanctions, Lending, and the Bank Ownership Channel*, with
  [Matteo Ficarra](https://sites.google.com/view/matteoficarra/home-page)
- Title only, no abstract needed unless I supply one.

### Teaching (teaching.html)

Geneva Graduate Institute (IHEID), Teaching Assistant, Sep 2024 – present:

- Macroeconomics I (Master) — Fall 2024, Fall 2025
- Microeconomics II (Master) — Spring 2025, Spring 2026

### CV (cv.html)

Short HTML summary so the content is crawlable and readable on a phone, plus a
prominent link to `files/cv.pdf`.

**Education**
- PhD Candidate in Economics, Geneva Graduate Institute (IHEID), Sep 2022 – present.
  Supervisor: Ugo Panizza. Second reader: Rui Esteves.
- MSc in Economics and Social Sciences, *cum laude*, Bocconi University, 2018–2021
- BSc in Economics and Social Sciences, Bocconi University, 2015–2018

**Positions**
- International Monetary Fund — Fund Internship Program, Jun–Aug 2026, Washington DC
- The World Bank Group — Visiting PhD Student, Jul–Aug 2025, Washington DC
- IHEID — Research Assistant to Prof. Rui Esteves (SNF project), Jan 2023 – Jun 2025
- The World Bank Group — Short-Term Consultant (part-time, remote), Jan–Jun 2023
- BAFFI CAREFIN, Bocconi — Research Assistant to Prof. Carlo Altomonte, Sep 2021 – Jun 2022
- UCLA Anderson — Research Assistant to Prof. Paola Giuliano (remote), Jul 2021 – Jun 2022
- European Commission, DG Competition — Trainee, Chief Economist Team, Feb–Jun 2021

**Grants and Scholarships**
- 2026 — Gallatin Excellence Scholarship, for one semester at a U.S. university
- 2022–2026 — Excellence Scholarship, Geneva Graduate Institute
- 2021 — Zegna Founder's Scholarship Program, Ermenegildo Zegna Group

**Languages** — Italian (native), English (fluent), Spanish (good)

**Software** — Stata, R, Dynare, LaTeX, Claude Code

Omit monetary amounts of scholarships from the web version. Omit date of birth,
citizenship, phone number, and home address entirely.

## 4. Design direction

Restrained and document-like. The job of this site is to make a small number of PDFs
and abstracts easy to find. Concretely:

- One accent colour, used only for links and one horizontal rule. No gradients.
- A serif or transitional face for body text at 18px or larger; one sans face for nav
  and metadata. Set a real type scale.
- Generous margins, measure capped around 70 characters. The research page must not
  sprawl edge to edge on a wide monitor.
- No hero image, no scroll animation, no parallax, no gallery, no timeline widget.
- Dark mode via `prefers-color-scheme`, using CSS custom properties.
- Respect `prefers-reduced-motion`. Visible keyboard focus states.
- A print stylesheet so the research page prints cleanly.

Avoid the current default look of AI-generated sites: cream background with a
terracotta accent, or near-black with a single acid accent. Derive the palette from the
subject instead, and tell me in one sentence why you chose it.

## 5. CV privacy — do this before publishing

The GitHub account is `guidoardizzone`, so the repo is `guidoardizzone.github.io` and
the site will live at `https://guidoardizzone.github.io`.

My current CV contains a **date of birth, a home street address, a mobile number, and
citizenship**. These are normal on a European CV and inappropriate on a page that
Google will index. Before anything goes in `files/`:

- Produce a web version of the CV with those four items removed. Keep the email.
- Drop the monetary amounts attached to scholarships.
- Keep the referees' names and titles but consider removing their email addresses,
  since publishing a senior colleague's address invites scraping. Ask me which I prefer.
- Show me a diff or a summary of what you removed before you commit the file.

Apply the same rules to `cv.html`.

## 6. Acceptance criteria

Verify each and report the result before telling me it's done:

1. `index.html` opens correctly from the filesystem with no server.
2. Every internal link resolves. No 404s, no placeholder `#` hrefs.
3. List every outstanding `TODO` still in the codebase.
4. Renders at 375px width with no horizontal scroll.
5. Fully readable with JavaScript disabled.
6. Each page has a unique `<title>` containing "Guido Ardizzone", plus a meta
   description and Open Graph tags.
7. No external network requests on page load.
8. Total page weight under 500KB excluding PDFs.
9. Repo contains a README explaining how to add a new paper entry.

## 7. Working style

- Propose the design plan (palette, type, layout) in writing before you write any CSS.
- Build the home page first, then stop for review before the other three.
- Commit in logical chunks with real commit messages.
