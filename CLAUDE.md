# CLAUDE.md

## What this is

A [Quarto](https://quarto.org) **website** for the two-day course
*"Data Wrangling & Summarizing in R"*, taught by Jessica Minnier, PhD, through
**NW NARCH** (Northwest Native American Research Centers for Health). It is an
intro-to-R course for trainees with no prior experience. Much of the course was
co-developed with **Meike Niederhausen**, who authored a large portion of the slides
(she is acknowledged in the slides and About page but is not the NARCH instructor of record).

- **Part 1:** Thursday, June 18, 2026, 9:00 a.m.–12:00 p.m. (Pacific)
- **Part 2:** Friday, June 19, 2026, 9:00 a.m.–12:00 p.m. (Pacific)
- **Location:** Morrison Meeting Room, Residence Inn Portland Downtown/RiverPlace, Portland, OR
- **Contact:** Dr. Minnier, minnier@ohsu.edu
- **Published site:** https://jminnier.github.io/NARCH_IntroR_2026_06/ (GitHub Pages from `docs/`)

This repo was adapted from the earlier OCTRI-BERD April 2026 workshop. The displayed
workshop content references NARCH; a few legacy `berd` references remain only as
citations of other/past workshops (BSTA 526 links, the Quarto_BERD_2025 workshop, the
ggplot source slides) and are intentionally kept.

## Build / render

- `quarto render` — renders the whole site to `docs/` (set via `output-dir` in `_quarto.yml`).
- `quarto preview` — live preview while editing.
- Output goes to `docs/` so the site can be served via GitHub Pages.
- Rendering is cached: `_freeze/` holds frozen computational output (`freeze: auto` —
  re-runs code only when source changes). `.quarto/` is the build cache (gitignored).

## Source files (`.qmd`)

| File | Purpose |
|------|---------|
| `index.qmd` | Home page — workshop dates, download links, setup instructions |
| `about.qmd` | Abstract, learning objectives, logistics |
| `slides_R_narch_2026.qmd` | The **revealjs** slide deck presented during the workshop |
| `slides_html_R_narch_2026.qmd` | Same slide content rendered as a scrollable **HTML webpage** |
| `code_Rintro_narch_2026.qmd` | Workshop code-along document (the website's rendered copy) |
| `solutions_practice.qmd` | Solutions to practice exercises |

Note: `slides_R_narch_2026.qmd` and `slides_html_R_narch_2026.qmd` share the same body
content but toggle the `format:` block (revealjs vs html). Keep their content in sync.

## Layout

- `data/` — workshop datasets (`.xlsx`): `toy_data`, `practice4_data`, `yrbss_demo`.
- `image/` — figures and screenshots used in slides/pages.
- `output/` — generated output artifacts.
- `docs/` — **rendered site output** (do not hand-edit; regenerate with `quarto render`).

## Student download zip

`R_code_Intro_NARCH_2026_06.zip` is the bundle attendees download from `index.qmd`.
It is **built from the sibling folder `../NARCH_IntroR_2026_06_code/`** (the student
working materials: the `.Rproj`, `code_Rintro_narch_2026.qmd`, `solutions_practice.qmd`,
`data/`, `output/` — excluding `.Rproj.user/`, `.DS_Store`, `.Rhistory`, and `test_quarto.*`).

The zip lives at the **website root** and is declared under `project.resources` in
`_quarto.yml`, so `quarto render` copies it into `docs/`. This matters: a full
`quarto render` otherwise **deletes** unrecognized files from `docs/`. To refresh the
zip after editing the code folder, rebuild it at the website root (folder-rooted so it
extracts to `R_code_Intro_NARCH_2026_06/`) and re-render. The home-page download link
points at `docs/R_code_Intro_NARCH_2026_06.zip` in the GitHub repo.

## Styling

- Site theme: `cosmo` + `brand`, with `styles.css` (`_quarto.yml`).
- Slides theme: `sky_modified_smaller_font.scss` (custom revealjs SCSS).

## Conventions

- RStudio project: `NARCH_IntroR.Rproj`. Indentation is 2 spaces, UTF-8.
- `.RData` / `.Rhistory` are committed by accident in some states but are gitignored going forward.
- When updating workshop dates/links, check `index.qmd` and `about.qmd` (and slide headers).
