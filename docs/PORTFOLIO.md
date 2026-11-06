# Lionnel Mazuba — portfolio maintenance

This site uses Al-Folio v1's gem-owned layouts: `al_folio_core` 1.0.15 and `al_folio_cv` 1.0.2. Dependencies, Ruby requirements, and deployment workflows are unchanged. No local layout, include, Sass, or JavaScript overrides were introduced.

## Content and navigation

The homepage is `_pages/about.md`. Navigation uses the theme's built-in About link, followed by Research, Publications, Projects, Experience, and CV (`nav_order: 1` through `5`). News remains available at `/news/` without a navigation item.

The three active projects have explicit, stable permalinks in `_projects/`. Cards use the theme's existing project include without images or unverified repository links. The overview lists broader technical areas without creating empty projects or claiming completed FPGA or AI accelerator work.

The configured neutral profile image is `assets/img/profile-placeholder.svg`. Alignment and circular presentation are retained from the original profile configuration.

## Personal information to add

- TODO: Replace the neutral placeholder with a personal photograph in `assets/img/`, then update `profile.image` in `_pages/about.md`. The previous `prof_pic.jpg` is Einstein's demonstration portrait and is excluded from the site.
- TODO: Supply a verified contact email, LinkedIn username, ORCID, and Google Scholar identifier if desired. Their empty fields in `_data/socials.yml` are commented out because `jekyll-socials` 0.0.7 would otherwise render links with missing identifiers. The email previously embedded in the About subtitle was unverified and has been removed.
- TODO: Add a verified personal CV PDF under `assets/pdf/`, then set `cv_pdf` in `_pages/cv.md` and optionally `_data/socials.yml`. The example PDF and Einstein CV output are excluded. There is currently no personal PDF download link.
- TODO: Add circuit diagrams, simulation results, or project repositories only when approved for public release. No quantitative results or implementation details have been inferred.
- TODO: Optionally supply a personal social preview image and set `og_image` in `_config.yml`. Open Graph text, author metadata, canonical URLs, sitemap, and robots configuration use the existing theme and plugins.

## Bibliography provenance

`_bibliography/papers.bib` is the publication source of truth for Jekyll Scholar. The solar paper's complete title, author ordering and names, conference, year, pages, and DOI were checked against the [publisher-deposited Crossref record](https://api.crossref.org/works/10.1109/ICECCME55909.2022.9988742) on 6 November 2026. The [paper DOI](https://doi.org/10.1109/ICECCME55909.2022.9988742) is used for the paper link.

The indexed author name is **Lionnel Mazuba Itetshi**. This published name is retained in the bibliography and CV publication entry; the website identity remains **Lionnel Mazuba**. Scholar's author-highlighting configuration recognises both forms. There are no unresolved required bibliographic fields for this entry.

The online CV uses `_data/cv.yml` with `cv_format: rendercv`. Custom section titles use the CV gem's supported bullet and label/details entries. Its publication renderer uses `publisher`, `url`, and `summary`, so these are included alongside the publication data. Graduation years use point-in-time `date` fields; no enrolment dates are assumed. `assets/json/resume.json` contains a minimal alternative identity and education record and is not the active CV format. Keep it aligned if expanding the JSONResume alternative.

## Year-only news

The four personal updates live in `_news/` with `year` and `order` fields. No exact publication, graduation, scholarship, or joining day is fabricated. Page-level Liquid in About and News renders this collection using the theme's table classes. The default announcement include always formats a month and day, so it is disabled on About. News collection documents have `output: false`; no individual date-based news pages are published. Use `order` only to control presentation within a year, not as an assertion of an exact date.

## Demo cleanup

The `_config.yml` exclusion list retains the original example posts, nine projects, three announcements, books, teachings, and unused pages in source for reference while preventing their publication. External demo feed ingestion, blog pagination and archives, publication badges, publication search, the site search control, masonry, and the reading progress bar are disabled. Plugins and their dependency pins are retained. Demonstration CV data, bibliography, social accounts, citation counts, venue links, and coauthor profiles have been replaced or cleared.

Sample PDF, notebook, media, HTML, and plot assets are excluded from publication; theme runtime assets remain intact. Removing navigation alone would not prevent pages from being built, which is why exclusions are explicit. After deploying, confirm old demo URLs return 404; the existing deployment action's normal output synchronization removes stale generated pages.

## Validation and deployment

This personal user site intentionally uses `url: https://maz-git-design.github.io` and `baseurl: ""`. The starter documentation's `/al-folio` path describes the upstream demo, not this root-hosted GitHub Pages site. Use the same plain Jekyll build as the existing deployment workflow; do not override the base URL with `/al-folio`.

With the repository's supported Ruby/Bundler environment and dependencies available:

```bash
bundle install
npm ci
npm run lint:prettier
npm run lint:style-contract
JEKYLL_ENV=production bundle exec jekyll build
bundle exec jekyll serve
```

Preview at `http://localhost:4000/`. Check the homepage, all six navigation entries, three project pages, the single publication, light/dark modes, mobile navigation, and `/sitemap.xml`. There should be no blog, book, teaching, or demo project output. The existing visual regression suite targets the upstream demonstration site and is not a suitable unchanged snapshot baseline for this personal portfolio.

Review and commit locally when ready:

```bash
git diff --check
git status --short
git add _config.yml _pages _projects _news _bibliography _data assets/json/resume.json assets/img/profile-placeholder.svg docs/PORTFOLIO.md
git commit -m "Personalize academic research portfolio for Lionnel Mazuba"
git push origin HEAD
```

The existing deployment workflow runs on pushes to `main` or `master`. No commit, push, or remote deployment is performed by the portfolio editing task.

## File inventory

Created:

- `_pages/research.md`, `_pages/experience.md`
- `_projects/sram-in-memory-computing.md`, `_projects/solar-charging-system.md`, `_projects/real-time-operating-system.md`
- `_news/research-assistant.md`, `_news/msc-completed.md`, `_news/chevening-scholarship.md`, `_news/iceccme-publication.md`
- `assets/img/profile-placeholder.svg`
- `docs/PORTFOLIO.md`

Modified:

- `_config.yml`
- `_pages/about.md`, `_pages/publications.md`, `_pages/projects.md`, `_pages/cv.md`, `_pages/news.md`
- `_bibliography/papers.bib`
- `_data/cv.yml`, `_data/socials.yml`, `_data/repositories.yml`, `_data/coauthors.yml`, `_data/venues.yml`, `_data/citations.yml`
- `assets/json/resume.json`

## Validation results for this edit

- Passed: `npm ci`, `npm run lint:prettier`, `npm run lint:style-contract`, and `git diff --check`.
- Passed source checks: duplicate-free configuration/data YAML, all 71 Markdown front matters, JSON/SVG syntax, explicit internal page links, referenced pinned-gem layouts/includes, navigation and CV section ordering, demo exclusions, three active projects, four year-only news entries, and one publication with a Crossref-matched DOI.
- Confirmed dependency files and all GitHub Actions workflows are unchanged.
- `bundle install` and `JEKYLL_ENV=production bundle exec jekyll build` were attempted but failed before Jekyll started: the host has Ruby 2.6.10 and lacks locked Bundler 4.0.6. The existing deployment workflow uses Ruby 3.3; use that supported environment for the remaining build checks. Docker is installed but its daemon is not running.
- Rendered homepage, publications, CV, project pages, generated links/sitemap, mobile layout, and light/dark browser behaviour remain unverified. No successful Jekyll build or visual test is claimed. Ruby-dependent integration and upgrade checks were not run.
