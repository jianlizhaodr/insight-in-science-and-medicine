# Insight in Science and Medicine

A topic-focused journal of notes, ideas, and commentary on science and medicine,
with linked references to primary literature.

## Structure

- `_biotech/` — Biotech entries (one Markdown file per entry, dated filename)
- `_bibliography/references.bib` — BibTeX references cited across entries
- `index.md` — Landing page listing recent entries across topics
- `biotech.md` — Topic index

Add new topics by creating a `_<topic>/` folder and registering it under
`collections:` in `_config.yml`.

## Writing an entry

Create a file like `_biotech/2026-04-22-my-entry.md`:

```markdown
---
title: "My entry title"
date: 2026-04-22
---

Body text. Cite a paper with {% raw %}{% cite key2024 %}{% endraw %}.

## References

{% raw %}{% bibliography --cited %}{% endraw %}
```

Add the corresponding entry to `_bibliography/references.bib`.

## Local preview

```bash
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000.

## Publishing

Pushes to `main` are built and deployed by `.github/workflows/deploy.yml`
to GitHub Pages. Enable Pages in repo Settings → Pages → Source: GitHub Actions.
