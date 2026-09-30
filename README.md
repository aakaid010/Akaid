# aakaid010.github.io

Personal academic website of **Kazi Ahsan Ahmed Akaid**, mechanical engineering
graduate of Chittagong University of Engineering & Technology (CUET), working on
prognostics and health management, explainable AI, and physics-informed machine
learning.

Live at <https://aakaid010.github.io/>

## Stack

Plain HTML, one CSS file, and a small vanilla JavaScript file. No build step, no
dependencies, no framework.

```
index.html          About, research interests, news, publications
research.html       Research overview, threads, current and earlier work
publications.html   Submitted papers and manuscripts in preparation
experience.html     Industrial experience, leadership, honours
cv.html             Web CV, links to the PDF
404.html            Not-found page
check.py            Consistency checker; run after every edit
assets/
  css/style.css     All styling; design tokens at the top
  js/main.js        Theme toggle, footer year, news collapse, back-to-top
  img/              Profile photo and favicon
  cv/               PDF CV
```

## Working on it

```bash
python -m http.server 4173   # preview at http://localhost:4173
python check.py              # broken links, dead anchors, nav drift
python check.py --write-sitemap   # after adding a page
```

See [CONTENT-GUIDE.md](CONTENT-GUIDE.md) for routine edits,
[AGENTS.md](AGENTS.md) for conventions, and [DECISIONS.md](DECISIONS.md) for
why the site is built this way.

## Deploying

1. Create a repository named exactly `aakaid010.github.io` on GitHub.
2. Push these files to the `main` branch.
3. Under *Settings, Pages*, set the source to **GitHub Actions**.

`.github/workflows/deploy.yml` runs `check.py` and publishes only if it passes.

## Replace the placeholder photo

`assets/img/profile.jpeg` is a generated "KA" monogram, not a real photo.
Replace it with a square photo (600x600 or larger) and keep the filename.
"# Akaid" 
"# Akaid" 
