# Content guide

Everything on this site is plain HTML. Edit a file, commit, push. GitHub Actions
checks it and publishes it automatically, usually within a minute.

**After any edit, run the checker:**

```bash
python check.py
```

To preview locally: `python -m http.server 4173`, then open
<http://localhost:4173>. If the checker fails in CI, the site is not deployed
and the previous version stays live.

## Where things live

| File | What it holds |
|---|---|
| `index.html` | Photo, bio, research interests, **News**, publications, contact |
| `research.html` | Overview, three research threads, current and earlier work |
| `publications.html` | Full publication list |
| `experience.html` | Industrial experience, leadership, honours |
| `cv.html` | Web version of the CV; links to the PDF |
| `assets/cv/` | The PDF CV |
| `assets/css/style.css` | All styling. Colours live in the `:root` block |
| `check.py` | Consistency checker; also regenerates `sitemap.xml` |

## Add a news item

In `index.html`, find `<!-- ===== NEWS` and paste this as the **first** `<li>`:

```html
<li>
  <time datetime="2026-11">Nov 2026</time>
  <p>Short sentence describing what happened.</p>
</li>
```

Past six items, older entries collapse behind a toggle automatically.

## Update a publication when it is accepted or published

Edit the `<article class="pub">` in **both** `publications.html` and `index.html`
(titles must match; `check.py` verifies this). Change the tag and venue line, and
add links inside a `.pub__actions` block:

```html
<div class="pub__actions">
  <a class="btn-link" href="https://doi.org/DOI-HERE" target="_blank" rel="noopener">DOI</a>
  <details class="bibtex">
    <summary>BibTeX</summary>
    <pre><code>@inproceedings{akaid2026key,
  author    = {Akaid, K. A. A. and Rabbi, S.},
  title     = {Title of the paper},
  booktitle = {Proceedings of ...},
  year      = {2026}
}</code></pre>
  </details>
</div>
```

`.pub__actions` and BibTeX belong on `publications.html` only; the homepage shows
a short teaser. Also update the `ItemList` JSON-LD in the `<head>` of
`publications.html` (add `datePublished` and `sameAs` once published).

Add a new paper by copying a whole `<article>` block, giving it a unique `id`.
Use `<span class="tag">Journal</span>` for journals and
`<span class="tag tag--muted">Conference</span>` for conferences, and wrap your
own name in `<span class="me">`.

## Add a project, award, or experience entry

```html
<div class="entry">
  <div class="entry__head">
    <h3 class="entry__title">Title</h3>
    <span class="entry__date">Jan 2027 &ndash; present</span>
  </div>
  <p class="entry__sub">Role or subtitle</p>
  <ul>
    <li>What you did.</li>
  </ul>
</div>
```

## Replace the CV PDF or the photo

- Overwrite `assets/cv/Kazi_Ahsan_Ahmed_Akaid_CV.pdf`, keeping the filename.
- Replace `assets/img/profile.jpeg` with a **square** image (600x600 or larger),
  keeping the filename.

## Editing the navigation

The nav and footer are copied into every page deliberately. If you add or rename
a page, edit the `<nav>` in **every** `.html` file, run `python check.py`, then
regenerate the sitemap with `python check.py --write-sitemap`.

## House style

- Never use an em dash (`&mdash;`). Use a colon, semicolon, comma, parentheses,
  or two sentences. En dashes only for ranges and compounds.
- British spelling in prose.
- Do not publish phone numbers or referees' contact details.

## Personal details used across the site

| Item | Value |
|---|---|
| Email | `akaid0001@gmail.com` |
| GitHub | `https://github.com/aakaid010` |
| Site URL | `https://aakaid010.github.io/` |
