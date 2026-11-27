# Agent instructions

Personal academic website for Kazi Ahsan Ahmed Akaid, a CUET mechanical
engineering graduate working on prognostics and health management (PHM),
remaining useful life (RUL) prediction, explainable AI, and uncertainty
quantification. The audience is prospective collaborators, supervisors, and
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
4. **`404.html` uses root-absolute paths with the `/Akaid/` project prefix**
   (`/Akaid/assets/css/style.css`, `/Akaid/index.html`), because the site is
   served from <https://aakaid010.github.io/Akaid/>. Root pages use relative paths.
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
  uncertainty quantification. Do not describe physics-informed ML as a
  research area. Additive manufacturing is listed on the homepage as an
  interest only; there is no AM work yet, so do not describe any.
- Do not describe unpublished work as published. Papers are labelled
  "submitted", "accepted", or "in preparation" until they appear in
  proceedings.

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
- Accepted: nanocellulose thesis paper (ICMIME 2026, RUET); turbofan RUL paper (ICMIEE 2026, KUET). Under review: tool wear journal manuscript, "Calibration Sources for Tool-Wear Prediction Intervals Under Tool and Machine Shift in Milling" (The International Journal of Advanced Manufacturing Technology, submitted Nov 2026, in peer review since 27 Nov 2026). Paper PDFs and the CV PDF are on Google Drive and linked from the pages
- Research Team Member, ELITE Research Lab, from Sep 2026 (protocol stage, experiments not yet run)
- IELTS Academic overall 7.5 (Listening 8.5, Reading 7.5, Writing 6.5, Speaking 7.0)
- Dean's List, 3 semesters; Organizing Secretary of RMA (2022&ndash;2025); ASME CUET member
- Private tutor, mathematics and physics, 2023&ndash;2025; BITAC industrial attachment, Dec 2025
- Email `akaid0001@gmail.com` &middot; GitHub `aakaid010`
- No Google Scholar, ORCID, or LinkedIn on file; do not add links until they exist
