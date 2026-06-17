# ziyinbin.com — Design System

> Single source of truth for the visual language of this site. Any agent or
> human editing the site should read this first and keep changes within these
> tokens. Distilled from three references: **kaiwenluo.me**, generic
> **Silicon-Valley engineer** personal-site conventions, and the patterns
> already built here. This file is excluded from the Jekyll build (see
> `_config.yml` `exclude:`), so it never ships to the website.

## 1. Philosophy

A "magazine + scholar" feel: an editorial **serif** for names, titles, and
quotes; a clean **sans** for prose and all UI/labels; a warm paper palette with
three restrained accents. Generous whitespace, hairline rules, no heavy borders,
no drop shadows except the one soft shadow under the hero photo.

The rule of thumb for serif vs sans:

- **Serif (Newsreader)** = proper nouns you'd italicize in print: the person's
  name, the *title* of a paper / talk / school / degree / project / course, and
  quotations.
- **Sans (Inter)** = everything else: body prose, section labels (eyebrows),
  dates, venues, coauthors, pills, nav, captions, buttons.

## 2. Fonts

| Role | Family | Used for |
|---|---|---|
| Sans (default) | **Inter** | body prose, eyebrows, metadata, pills, nav, captions, UI |
| Serif (editorial) | **Newsreader** | hero name, entry titles, quotes (italic) |
| CJK serif | **Noto Serif SC** | the Chinese name 宾梓吟 only |
| (favicon only) | Cormorant Garamond italic | the `b` mark — not used in page text |

SCSS variables live in `_sass/_themes.scss`:
`$serif`, `$sans-serif`, `$global-font-family` (= sans), `$header-font-family`
(= sans). Serif is applied **per component**, never globally. Fonts are loaded in
`_includes/head/custom.html`.

## 3. Type scale (rem)

| Token | Size | Weight | Family | Notes |
|---|---|---|---|---|
| Hero name | 3.7 (mobile 2.6) | 500 | serif | `.home-hero__name`; Chinese span 500 Noto Serif SC |
| Entry title | 1.18–1.26 | 500 | serif | paper/talk/school/project/course titles |
| Body prose | 1.0–1.05 | 400 | sans | line-height **1.72**; muted via `--global-text-color-light` |
| **Section eyebrow (h2)** | **0.8** | **600** | **sans** | UPPERCASE, tracking **0.14em**, **navy** |
| **Mini-eyebrow (h3 / .eyebrow)** | **0.72** | **500** | **sans** | UPPERCASE, tracking **0.14em**, **rust** |
| Metadata | 0.82–0.88 | 400 | sans | dates, venues, coauthors → muted-ink |
| Fine print / blurb | 0.78 | 400 | sans | → light-ink |
| Pill | 0.78 | 500 | sans | tracking 0.01em |

Two heading tiers only: **section eyebrow** (navy, the bigger one) and
**mini-eyebrow** (rust, the smaller one). Do not invent a third size.

## 4. Color tokens

Defined as CSS custom properties in `_sass/theme/_default_light.scss` and mirrored
for dark mode in `_sass/theme/_default_dark.scss`. **Always reference the
`--global-*` variables — never hard-code a hex in a component**, or dark mode
breaks.

| Token | Light | Role |
|---|---|---|
| `--global-bg-color` | `#FBFAF6` paper | page background |
| `--global-text-color` | `#1F1A12` ink | primary text, entry titles |
| `--global-text-color-light` | `#57534E` | body prose, blurbs |
| `--global-muted-text-color` | `#3D372A` | dates, coauthors, attributions |
| `--global-link-color` | `#1F3344` navy | links, **section headings**, outline pills, card/quote accents |
| `--global-highlight-color` | `#8C3818` rust | mini-eyebrows, **section accent bars**, link hover |
| `--global-accent-color` | `#B5853A` amber | name middot |
| `--global-accent-bg` / `--global-accent-text` | `#F0E7D0` / `#8C5E1F` | accent pill (venue/journal) |
| `--global-border-color` | `rgba(31,26,18,.12)` | the hairline rule |

Accent usage discipline: **navy** is structure (links, headings, primary pills);
**rust** is emphasis (mini-eyebrows, accent bars, hover); **amber** is a single
decorative touch (the name middot, the venue pill). Don't spread them further.

## 5. Section heading (the canonical pattern)

Every page's section headings look identical — the CV style:

- sans, UPPERCASE, **0.8rem / 600 / 0.14em**, color **navy**
- a thin **top hairline** (`1px var(--global-border-color)`) + generous top margin
- a short **rust accent bar** underneath via `::after` (2px tall × ~2.4rem, radius 999px)
- **no** full-width bottom border

Implemented by `.cv-page h1` (`_sass/include/_cv.scss`) and `.page__content h2`
(`_sass/layout/_page.scss`) — keep these two in sync. Markdown `##` on Home /
Miscellaneous and the Liquid `<h2>` on Publications all resolve to
`.page__content h2`, so they inherit it for free.

## 6. Divider tokens (only four — do not add more)

1. **Hairline** — `1px solid var(--global-border-color)`. Entry separators,
   section top rules, footer. The default.
2. **Section accent bar** — rust `::after`, 2px × ~2.4rem, radius 999px. Only
   under section headings (§5).
3. **Quote rule** — `2px` navy `border-left`. Only on `.motto`.
4. **Card frame** — `1px` light box + `3px` navy `border-left`. Only on
   `.publication-card`.

## 7. Components

- **Outline pill** — white bg, `1px` navy border, navy text, radius 999px,
  0.78rem sans 500. Topic chips (hero), sidebar bio tags, status pills.
  (`.pill--status`, `.home-hero__chips span`, `.author-bio-pill`.)
- **Accent pill** — amber-tint bg, amber-dark text. Venue / journal only.
  (`.pill--venue`.)
- **Role line** — plain navy sans text, **not** a pill. "PhD Candidate,
  Operations Management". (`.home-hero__chips span:first-child`,
  `.author-bio-pill--primary`.)
- **Entry** — serif title + sans meta; optional right-aligned italic date;
  hairline separator between entries. (`.talk-entry`, CV bullets.)
- **Quote** — serif italic + 2px navy left rule; attribution in sans muted with a
  leading em-dash. (`.motto` + `.motto .attribution`, in `_sass/include/_pills.scss`.)
- **Publication card** — serif title, sans coauthors (smaller), sans blurb
  (smallest), pill row; numbered counter; card frame (§6.4).
  (`.publication-card` in `_sass/include/_pills.scss`.)

## 8. Navigation

Brand on the left — rounded-navy `b` mark (~1.15em, `rx=15` square) + "Ziyin Bin";
nav items + theme-toggle gear pushed to the right (kaiwenluo layout). The brand
is a flex sibling of the greedy-nav, not inside it (see `_includes/masthead.html`
+ `_sass/layout/_masthead.scss`). Nav order: **Home · Research · CV ·
Miscellaneous**.

## 9. Page architecture

- `/` (`_pages/about.md`, `body_class: landing`) — sparse hero (no sidebar),
  centered ~1120px column, then Upcoming Talks. Full bio.
- `/home/` (`_pages/home.md`) — sidebar layout, full bio, Working Papers,
  Upcoming Talks, Contact.
- `/cv/` (`_pages/cv.md`, `.cv-page` wrapper) — the canonical section-heading
  reference. `.cv-page strong` is serif (entry titles).
- `/publications/`, `/miscellaneous/` — sidebar layout, `.page__content` headings.
- `/field-maps/<slug>/` — standalone self-contained HTML pages (own styling,
  out of scope for these tokens).

## 10. Do / Don't

- **Do** reference `--global-*` tokens; **don't** hard-code hex in components.
- **Do** keep all SCSS comments ASCII (the kramdown-era Sass compiler throws
  `Invalid US-ASCII character` on a non-ASCII byte — no em-dashes / middots in
  `.scss`).
- **Do** use the two heading tiers only (navy section eyebrow, rust mini-eyebrow).
- **Don't** add a new divider style; reuse one of the four in §6.
- **Don't** put serif on body prose or sans on the hero name.

## Where each token lives

| Concern | File |
|---|---|
| Font variables + global family | `_sass/_themes.scss` |
| Color tokens (light / dark) | `_sass/theme/_default_light.scss`, `_default_dark.scss` |
| Font loading | `_includes/head/custom.html` |
| Section headings, mini-eyebrows | `_sass/layout/_page.scss`, `_sass/include/_cv.scss` |
| Pills, publication cards, motto, eyebrow | `_sass/include/_pills.scss` |
| Hero, talk entries, landing layout | `_sass/include/_home.scss` |
| Sidebar bio pills | `_sass/layout/_sidebar.scss` |
| Nav / brand | `_includes/masthead.html`, `_sass/layout/_masthead.scss`, `_sass/layout/_navigation.scss` |
| Favicon | `images/favicon.svg` (+ generated PNGs/ICO) |

## Local build

```bash
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"
cd "/Users/bzy/Documents/baidu_snyc/Personal Website"
bundle exec jekyll serve   # http://127.0.0.1:4000
```
