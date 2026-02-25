# Adding Publications & Presentations to Your Site

This guide walks through how to add new entries to the Publications & Presentations page.

---

## How the page works

Every entry lives in `content/publication/` as its own folder containing an `index.md` file. The Publications page automatically splits entries into two sections:

- **Publications** — any entry *without* `is_presentation: true`
- **Presentations** — any entry *with* `is_presentation: true`

Entries are grouped by year within each section, newest first.

---

## Adding a Journal Article

1. Create a new folder inside `content/publication/`. Use a short, descriptive name with no spaces or special characters. A good convention is `lastname-keyword-year` (e.g., `aringer-personality-2025`).

2. Inside that folder, create a file named `index.md`.

3. Paste the following template and fill in your details:

```yaml
---
title: 'Your Full Article Title Here'
author: 'Aringer, A., Collaborator, B., & Senior, C.'
date: '2025-04-01'
publishDate: '2025-04-01T00:00:00Z'
publication_types:
- article-journal
publication: '*Journal of Full Name Here*'
abstract: |
  Paste your abstract here. It can span multiple lines.
  Just keep each line indented by two spaces.
tags:
- Personality
- Health Psychology
featured: false
url_pdf: ''
url_html: ''
url_bib: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_slides: ''
image: ''
---
```

4. Fill in each field (see **Field Reference** below for what each does).

5. Any field left as `''` (empty string) will simply not appear as a button on the page — no need to delete unused fields.

---

## Adding a Conference Paper or Book Chapter

Same steps as a journal article, but change `publication_types` to one of:

| Type | Badge shown |
|------|-------------|
| `article-journal` | Journal Article |
| `paper-conference` | Conference Paper |
| `book-chapter` | Book Chapter |
| `preprint` | Preprint |
| `thesis` | Thesis |

---

## Adding a Talk or Oral Presentation

1. Create a new folder inside `content/publication/` (e.g., `aps-talk-2025`).

2. Create `index.md` inside it with this template:

```yaml
---
title: 'Your Talk Title Here'
author: 'Aringer, A., & Collaborator, B.'
date: '2025-05-15'
publishDate: '2025-05-15T00:00:00Z'
is_presentation: true
publication_types:
- talk
publication: '*Conference Name, City, State*'
abstract: |
  Optional abstract or brief description of the talk.
tags:
- Personality
- Stress
featured: false
url_pdf: ''
url_slides: ''
url_video: ''
---
```

The key difference from a publication is the line:
```yaml
is_presentation: true
```
This routes the entry to the **Presentations** section instead of **Publications**.

| Presentation type | Badge shown |
|-------------------|-------------|
| `talk` | Talk |
| `invited-talk` | Invited Talk |
| `poster` | Poster |
| `workshop` | Workshop |

---

## Adding a Poster

Same as a talk, but set `publication_types` to `poster`:

```yaml
is_presentation: true
publication_types:
- poster
```

---

## Adding a Figure or Graph Preview

Each entry can display a small thumbnail image on the right side of the entry. To use this:

1. Place your image file (PNG or JPG) inside the same folder as the `index.md`. Name it something clear like `figure1.png`.

2. Set the `image` field to the filename (just the filename, not the full path):

```yaml
image: 'figure1.png'
```

The image will appear as a small preview (~130px wide) alongside the entry on the publications page.

---

## Attaching Files (PDF, BIB, Slides, etc.)

For files you want to make directly downloadable (PDFs, .bib files, poster files):

1. Place the file in the `static/uploads/` folder (create this folder if it doesn't exist yet). Example path: `static/uploads/aringer-2025-personality.pdf`

2. Reference it in your `index.md` using the `/uploads/` path:

```yaml
url_pdf: '/uploads/aringer-2025-personality.pdf'
url_bib: '/uploads/aringer-2025-personality.bib'
url_poster: '/uploads/aringer-2025-poster.pdf'
```

For links that live externally (DOI, OSF, GitHub, journal HTML), paste the full URL directly:

```yaml
doi: 10.1037/pspp0000123
url_html: 'https://journals.apa.org/doi/...'
url_code: 'https://github.com/yourusername/repo'
url_dataset: 'https://osf.io/abc123/'
```

---

## Field Reference

| Field | What it does |
|-------|-------------|
| `title` | Full title of the work |
| `author` | Authors as a formatted string (displayed as-is) |
| `date` | Publication/presentation date in `YYYY-MM-DD` format; controls year grouping |
| `publishDate` | Hugo internal date; set to same as `date` |
| `is_presentation` | Set to `true` to place in Presentations section; omit or set `false` for Publications |
| `publication_types` | List with one type (see tables above) |
| `publication` | Venue name; wrap in `*asterisks*` to italicize |
| `abstract` | Abstract text; use `\|` and indent subsequent lines |
| `tags` | List of keyword tags shown as small badges |
| `featured` | Set `true` to show on the homepage featured section |
| `doi` | DOI without the `https://doi.org/` prefix (e.g., `10.1037/abc123`) |
| `url_pdf` | Path or URL to the PDF |
| `url_html` | URL to the HTML version on the publisher's site |
| `url_bib` | Path to a `.bib` citation file |
| `url_code` | URL to code repository |
| `url_dataset` | URL to dataset (OSF, etc.) |
| `url_poster` | Path or URL to poster PDF |
| `url_slides` | Path or URL to slide deck |
| `url_video` | URL to video recording |
| `image` | Filename of a figure image placed in the same folder (for thumbnail preview) |

---

## Quick checklist

- [ ] Created a new folder under `content/publication/`
- [ ] Created `index.md` inside that folder
- [ ] Set `is_presentation: true` if it's a talk or poster
- [ ] Set the correct `publication_types` value
- [ ] Set `date` to the correct year (controls which year group it appears under)
- [ ] Filled in `doi` or `url_*` fields for any links you want to show
- [ ] Placed any downloadable files in `static/uploads/` and referenced them with `/uploads/filename`
- [ ] Placed any figure image in the entry's folder and referenced it with just the `filename`
