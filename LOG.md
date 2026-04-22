# Project Log — Insight in Science and Medicine

## 2026-04-22 — Initial launch

### Infrastructure
- **Repo**: https://github.com/jianlizhaodr/insight-in-science-and-medicine (public)
- **Live site**: https://jianlizhaodr.github.io/insight-in-science-and-medicine/
- **Stack**: Jekyll 4.3 + Minima theme + jekyll-scholar (BibTeX) + GitHub Pages via Actions
- **GitHub CLI**: v2.91.0 installed locally; authenticated as `jianlizhaodr`
- **Deploy**: pushes to `main` trigger `.github/workflows/deploy.yml` → build → Pages

### Journal identity
- **Title**: Insight in Science and Medicine
- **Publisher**: Insight in Science and Medicine Publishing Group
- **ISSN**: 3069-8898 (U.S. ISSN Center) (Online)
- **DOI prefix**: 10.65587
- **License**: CC BY 4.0
- **Brand color**: `#0b2c5a` (dark blue)

### Content model
- Collections per topic (currently: `biotech/`)
- Entry frontmatter fields:
  - `title` (required)
  - `date` (required)
  - `doi` (required) — pattern `10.65587/isam.YYYY.NNN`; URL derives from this
  - `type` — e.g. `Article`, `Review`, `Perspective` (default: `Article`)
  - `access` — e.g. `Open Access`, `FREE` (default: `Open Access`)
  - `authors` — e.g. `Zhao et al.`
  - `image` — relative path to thumbnail for card
  - `category` — journal/section name displayed on card
  - `featured: true` — pin to "Featured content" section
- URL pattern: `/biotech/<doi>/` e.g. `/biotech/10.65587/isam.2026.001/`
- Citations: BibTeX in `_bibliography/references.bib`; cite with `{% cite key %}`, render with `{% bibliography --cited %}`

### File layout
```
insight-in-science-and-medicine/
├── _config.yml              # site config, collections, scholar
├── Gemfile                  # jekyll, jekyll-scholar, plugins
├── _bibliography/
│   └── references.bib       # BibTeX store
├── _biotech/                # biotech collection
│   └── 2026-04-22-welcome.md
├── _includes/
│   └── article-card.html    # reusable card component
├── assets/
│   └── main.scss            # custom styles (dark blue theme, cards, hero)
├── index.md                 # homepage: hero + featured + online now
├── biotech.md               # biotech topic index
├── about.md
├── README.md
├── LOG.md                   # this file
└── .github/workflows/deploy.yml
```

### Homepage sections (top to bottom)
1. Tagline (dark blue): "A peer-reviewed journal of translational research..."
2. Hero row (3 cols): Cover+Issue info | Action buttons | Journal metrics
3. Featured content (grey bg): 4 cards, filters by `featured: true`
4. Online now: 4 most-recent cards
5. Publication Information list

### Open items / to improve
- [ ] Add real cover image to hero (replace dark blue gradient placeholder)
- [ ] Set real journal metric values (currently "—")
- [ ] Add more entries so Featured/Online now grids populate properly
- [ ] Create additional topic collections (medicine, neuroscience, etc.)
  - Create `_<topic>/` folder
  - Register in `_config.yml` under `collections:` and `defaults:`
  - Create `<topic>.md` topic index page (copy `biotech.md`)
- [ ] Add per-article thumbnail images under `/assets/images/`
- [ ] Populate `_bibliography/references.bib` with real citations
- [ ] Consider custom domain (e.g., `insight-sci-med.org`)
- [ ] Set up DOI registration via a DOI registrar (Crossref, DataCite) — the `10.65587` prefix must be officially assigned
- [ ] Journal metrics: decide source (editorial system vs. manual)
- [ ] Add Submit / Aims & Scope / Info for authors pages (currently all link to about.md)
- [ ] Email alerts signup (needs 3rd-party service: Mailchimp, Buttondown, etc.)
- [ ] Consider replacing Minima with a more academic theme later (al-folio, Academic Pages)

### How to add a new entry
1. Pick next DOI number: `10.65587/isam.2026.NNN`
2. Create `_biotech/YYYY-MM-DD-slug.md`:
   ```yaml
   ---
   title: "..."
   date: 2026-MM-DD
   doi: 10.65587/isam.2026.NNN
   type: Article
   access: Open Access
   authors: Author et al.
   image: /assets/images/fig.png    # optional
   featured: true                    # optional
   ---
   Body with {% raw %}{% cite key2024 %}{% endraw %}.
   ## References
   {% raw %}{% bibliography --cited %}{% endraw %}
   ```
3. Add new BibTeX entry to `_bibliography/references.bib` if needed
4. Drop image file under `assets/images/` if using a thumbnail
5. `git add . && git commit -m "Add entry: <title>" && git push`
6. GitHub Actions rebuilds and deploys in ~1 minute

### Commit history highlights
- `0667cdd` Initial scaffold
- `2951120` Set site URL and repo links to jianlizhaodr
- `02a00e9` Update description with ISSN
- `7949929` Style site description in dark blue
- `c1559a7` Update description; style site title in dark blue
- `2f65390` Add journal tagline to home page in dark blue
- `adeaee7` Add Publication Information section
- `9dd2b85` Switch to DOI-style permalinks
- `3ac6d45` Redesign Most recent section as card grid
- `7a9b76d` Rebuild homepage: Cell-style hero, featured content, online now sections
