# CLAUDE.md

## What this is

A [Quarto](https://quarto.org) **website** for the workshop *"Getting Started in R and RStudio"*,
taught by Jessica Minnier & Meike Niederhausen (OHSU OCTRI-BERD). It is a two-part
interactive intro-to-R workshop for attendees with no prior experience.

This repo is the **NARCH June 2026** offering, adapted from the earlier BERD April 2026
version (some file/link names still reference `BERD_2026_04`).

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
| `about.qmd` | Abstract and workshop description |
| `slides_R_berd_2026.qmd` | The **revealjs** slide deck presented during the workshop |
| `slides_html_R_berd_2026.qmd` | Same slide content rendered as a scrollable **HTML webpage** |
| `code_Rintro_narch_2026.qmd` | Current workshop code-along document (NARCH 2026 version) |
| `code_Rintro_berd_2026.qmd` | Prior BERD version of the code-along (being phased out) |
| `solutions_practice.qmd` | Solutions to practice exercises |

Note: `slides_R_berd_2026.qmd` and `slides_html_R_berd_2026.qmd` share the same body
content but toggle the `format:` block (revealjs vs html). Keep their content in sync.

## Layout

- `data/` — workshop datasets (`.xlsx`): `toy_data`, `practice4_data`, `yrbss_demo`.
- `image/` — figures and screenshots used in slides/pages.
- `output/` — generated output artifacts.
- `docs/` — **rendered site output** (do not hand-edit; regenerate with `quarto render`).
  Includes `R_code_Intro_BERD_2026_04.zip`, the bundle of workshop files attendees download.

## Styling

- Site theme: `cosmo` + `brand`, with `styles.css` (`_quarto.yml`).
- Slides theme: `sky_modified_smaller_font.scss` (custom revealjs SCSS).

## Conventions

- RStudio project: `NARCH_IntroR.Rproj`. Indentation is 2 spaces, UTF-8.
- `.RData` / `.Rhistory` are committed by accident in some states but are gitignored going forward.
- When updating workshop dates/links, check `index.qmd` and `about.qmd` (and slide headers).
