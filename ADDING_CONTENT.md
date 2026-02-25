# Adding Publications & Presentations to Your Site

All publications and presentations are managed in a **single file**:

```
data/publications.yaml
```

Open that file, add a new entry to the appropriate list, save, and you're done.

---

## File structure

The YAML file has two top-level lists:

```yaml
publications:
  - title: "..."
    ...

presentations:
  - title: "..."
    ...
```

Entries in `publications:` appear in the **Publications** section of the page.
Entries in `presentations:` appear in the **Presentations** section.
Both sections are grouped and sorted by year automatically.

---

## Adding a Journal Article

Open `data/publications.yaml`, scroll to the `publications:` list, and append a new entry:

```yaml
  - title: "Your Full Article Title"
    author: "Aringer, A., Collaborator, B., & Senior, C."
    year: 2025
    type: "article-journal"
    venue: "*Journal of Full Name Here*"
    abstract: "Paste your abstract here as a single line, or leave blank."
    tags: [Personality, Health Psychology]
    featured: false
    doi: "10.1037/pspp0000123"
    url_pdf: ""
    url_html: ""
    url_bib: ""
    url_code: ""
    url_dataset: ""
    url_poster: ""
    url_slides: ""
    image: ""
```

Any field left as `""` (empty string) simply won't appear as a button on the page.

---

## Publication types

Set `type:` to one of the following — this controls the badge shown on the page:

| `type` value | Badge shown |
|---|---|
| `article-journal` | Journal Article |
| `paper-conference` | Conference Paper |
| `book-chapter` | Book Chapter |
| `preprint` | Preprint |
| `thesis` | Thesis |

---

## Adding a Talk or Oral Presentation

Open `data/publications.yaml`, scroll to the `presentations:` list, and append:

```yaml
  - title: "Your Talk Title"
    author: "Aringer, A., & Collaborator, B."
    year: 2025
    type: "talk"
    venue: "*Conference Name, City, ST*"
    abstract: ""
    tags: [Personality, Stress]
    featured: false
    doi: ""
    url_pdf: ""
    url_slides: ""
    url_poster: ""
    url_video: ""
    image: ""
```

---

## Adding a Poster

Same as a talk, just change `type`:

```yaml
    type: "poster"
```

Presentation types available:

| `type` value | Badge shown |
|---|---|
| `talk` | Talk |
| `invited-talk` | Invited Talk |
| `poster` | Poster |
| `workshop` | Workshop |

---

## Featuring a publication on the homepage

Set `featured: true` on any entry under `publications:` to have it appear in the **Featured Publications** section on the homepage. The most recent 5 publications also appear in the **Recent Publications** section regardless of this setting.

---

## Adding downloadable files (PDF, BIB, Poster, etc.)

1. Place the file in the `static/uploads/` folder (create this folder if it doesn't exist). Example: `static/uploads/aringer-2025-personality.pdf`

2. Reference it in the entry using the `/uploads/` path:

```yaml
    url_pdf: "/uploads/aringer-2025-personality.pdf"
    url_bib: "/uploads/aringer-2025-personality.bib"
    url_poster: "/uploads/aringer-2025-poster.pdf"
```

For links that live externally (DOI, OSF, GitHub, publisher HTML), paste the full URL:

```yaml
    doi: "10.1037/pspp0000123"
    url_html: "https://journals.apa.org/doi/..."
    url_code: "https://github.com/yourusername/repo"
    url_dataset: "https://osf.io/abc123/"
```

---

## Adding a figure or graph preview

To show a small thumbnail image alongside an entry:

1. Place your image (PNG or JPG) in `static/uploads/`. Example: `static/uploads/aringer-2025-figure1.png`

2. Set the `image` field to the full `/uploads/` path:

```yaml
    image: "/uploads/aringer-2025-figure1.png"
```

The image will appear as a ~130px thumbnail on the right side of the entry.

---

## Field reference

| Field | What it does |
|---|---|
| `title` | Full title of the work |
| `author` | Author string, displayed as-is |
| `year` | Four-digit year; controls which year group the entry appears under |
| `type` | Entry type — determines the badge shown (see tables above) |
| `venue` | Journal or conference name; wrap in `*asterisks*` to italicize |
| `abstract` | Optional abstract text |
| `tags` | List of keyword tags shown as small badges |
| `featured` | `true` to show on the homepage Featured section (publications only) |
| `doi` | DOI without the `https://doi.org/` prefix |
| `url_pdf` | Path or URL to the PDF |
| `url_html` | URL to the HTML version on the publisher's site |
| `url_bib` | Path to a `.bib` citation file |
| `url_code` | URL to code repository |
| `url_dataset` | URL to dataset (OSF, etc.) |
| `url_poster` | Path or URL to poster PDF |
| `url_slides` | Path or URL to slide deck |
| `url_video` | URL to video recording |
| `image` | `/uploads/` path to a figure image for the thumbnail preview |

---

## Quick checklist

- [ ] Opened `data/publications.yaml`
- [ ] Added the new entry to the correct list (`publications:` or `presentations:`)
- [ ] Set the correct `year` (controls year grouping)
- [ ] Set the correct `type` (controls badge)
- [ ] Filled in `doi` or `url_*` fields for any links to show
- [ ] Placed any downloadable files in `static/uploads/` and referenced them with `/uploads/filename`
- [ ] Placed any figure image in `static/uploads/` and set `image: "/uploads/filename"`
