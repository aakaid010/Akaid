# Agent instructions

Personal academic website for Kazi Ahsan Ahmed Akaid, a CUET mechanical
engineering graduate working on prognostics and health management (PHM),
remaining useful life (RUL) prediction, explainable AI, and physics-informed
machine learning. The audience is prospective collaborators, supervisors, and
graduate programmes, so the site must read as a researcher's page: plain, quiet,
and fast, not a developer portfolio.

## Hard rules

1. **No build step, no dependencies, no frameworks.** Plain HTML, one CSS file,
   one small vanilla JS file. The only external request is Google Fonts, and
   every font has a local fallback stack.
2. **Run `python check.py` after every change.** CI runs it too; a failure
   blocks deploy.
3. **The `<nav>` and `<footer>` blocks are byte-identical across all pages,**
   on purpose. If you touch one, touch all of them and let `check.py` confirm.
4. **`404.html` uses root-absolute paths** (`/assets/css/style.css`,
   `/index.html`). Root pages use relative paths.
5. **Colours are defined in three places** in `assets/css/style.css`: the
   `:root` block, the `@media (prefers-color-scheme: dark)` block, and the
   `:root[data-theme="dark"]` block. Change all three together.
6. **Keep text contrast at 4.5:1 or better** in both themes.
7. **Never persist a theme to `localStorage` on page load.** Only on an
   explicit click.
8. **Do not publish personal contact details beyond email.** No phone number,
   home address, or referees' contact details on the site. Those stay in the PDF
   CV only.
9. **The theme toggle is a sibling of `.site-nav__links`, not inside it.**
10. **No em dashes anywhere.** Use a colon, semicolon, comma, parentheses, or a
    full stop. En dashes only for ranges and compounds (`2022&ndash;2026`,
    `CNN&ndash;LSTM`). `grep -c mdash *.html` must return zero.
11. **Write CSS escapes with six hex digits** (`"\0000B7"`).

## Tone and content

- Understated and factual. No marketing language, no emoji, no exclamation
  marks, and no claims the CV does not support.
- British spelling in prose (generalisation, modelling). Paper titles keep the
  spelling used by the authors ("Modeling").
- Research framing: one question, building data-driven models for engineering
  systems that can be trusted (validated without leakage, honest about
  uncertainty, with explanations that agree), across three threads: prognostics
  and RUL prediction, explainable AI and explanation agreement, and
  physics-informed and uncertainty-aware machine learning.
- Do not describe unpublished work as published. Papers are labelled
  "submitted" or "in preparation" until they appear in proceedings.

## Layout

```
index.html            About, interests, news, publications
research.html         Overview, three threads, current and earlier work
publications.html     Submitted papers and manuscripts; ItemList JSON-LD in <head>
experience.html       Industrial experience, leadership, honours
cv.html               Web CV; links to the PDF
404.html              Not-found page
check.py              Consistency checker; also regenerates sitemap.xml
assets/css/style.css  All styling
assets/js/main.js     Theme, dates, news collapse, BibTeX copy, back-to-top
.github/workflows/    Check-then-deploy to GitHub Pages
```

## Reusable components

| Class | Use |
|---|---|
| `.entry` + `.entry__head/__title/__date/__sub` | A dated CV-style item |
| `.timeline` wrapping `.entry` items | Vertical rail with a node per entry |
| `.pub` + `.pub__title/__authors/__venue` | A publication record |
| `.tag`, `.tag--muted` | Journal / Conference chips above the title |
| `.rows` + `.row` (`<dl>`) | Label-and-value pairs, e.g. skills |
| `.news` | Dated news list on the homepage |
| `.callout` + `.btn` | Boxed row with an action, e.g. CV download |

## Facts

Do not invent credentials. Current, verified values:

- B.Sc. Mechanical Engineering, CUET, Feb 2022 &ndash; Jul 2026, CGPA 3.55/4.00,
  final four-semester average 3.80/4.00
- Thesis: Predictive Modeling of Nanocellulose Characteristics from Acid
  Hydrolysis Process Parameters Using Machine Learning
- Submitted: nanocellulose thesis paper (no venue on the CV); ICMIEE 2026 (KUET) turbofan RUL paper. In preparation: tool wear journal manuscript (CNC milling)
- Research Intern, ELITE Research Lab, from Sep 2026
- Dean's List, 3 semesters; Organizing Secretary of RMA; ASME CUET member
- Email `akaid0001@gmail.com` &middot; GitHub `aakaid010`
- No Google Scholar, ORCID, or LinkedIn on file; do not add links until they exist
