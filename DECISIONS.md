# Decision log

Why this site looks and works the way it does. `AGENTS.md` holds the rules; this
file holds the reasoning.

Last updated: 1 October 2026.

## Who this is for

Kazi Ahsan Ahmed Akaid, a mechanical engineering graduate of CUET. The audience
is supervisors, graduate admissions committees, and collaborators in PHM and
machine learning for engineering. Every design decision is judged by one
question: does this help a busy academic reader find the research?

## The research narrative

The work spans materials data (nanocellulose), turbofan engines (C-MAPSS), and cutting-tool wear in CNC milling. These are one line of work, not three: in each, the
question is whether a data-driven model can be trusted. The site states that
question once, on the research page, and shows three threads: prognostics and
RUL prediction, explanation agreement, and physics-informed and
uncertainty-aware learning. Keep that thread when rewriting About or Research.

## Deliberate omissions

- **No phone number, home address, or referees' contact details** on the site.
  They live in the PDF CV only.
- **No claim of publication.** Both conference papers are submitted and the tool wear journal paper is in preparation, and the site says so. No DOI, BibTeX, or
  `datePublished` is given until a paper appears in proceedings.
- **Thesis supervisor is not named** on the site, because the CV lists Dr. Md.
  Sanaul Rabbi as academic advisor without stating his thesis role.
- **No Google Scholar, LinkedIn, or ORCID links**, because none are on the CV.

## Architecture

| Decision | Why |
|---|---|
| Plain HTML, one CSS file, one small JS file, no build step | Content volume is small, and nothing can break during application season. |
| Nav and footer duplicated on every page | Injecting them with JS would hide them from search engines. `check.py` detects drift. |
| Deploy through GitHub Actions | It lets `check.py` gate the deploy, so a broken edit fails the build instead of taking the live site down. |
| Nav slot "Experience" (`experience.html`) | Holds industrial training, leadership, and honours, which do not fit the research pages. |

## Design

The layout, typography, and dark mode are inherited from the reference academic
template and are unchanged. Running text uses the full 890px column by choice;
do not narrow it without asking the site owner.
