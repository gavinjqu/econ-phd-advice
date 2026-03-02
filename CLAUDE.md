# Econ PhD Advice — Project Guide for Claude Code

## Project Overview

This is a community-maintained, open-source collection of resources and advice for PhD students in economics — and for undergrads considering a PhD. It was originally a Google Sites page (https://sites.google.com/view/econgradadvice/) created by Chris Roth and David Schindler. We are migrating it to a **Quarto website** hosted on GitHub Pages so the community can contribute via pull requests and issues. We are also expanding the scope to include resources for undergraduates exploring the path to an econ PhD, drawing on sources like Aaron C. Watt's advice page (https://acwatt.net/advice/) and others.

## Tech Stack

- **Quarto** (≥1.4) — static site generator using Markdown (`.qmd`) files
- **GitHub Pages** — hosting (deployed from `gh-pages` branch via GitHub Actions)
- **GitHub Actions** — CI/CD for building and deploying the site, plus link checking

## Project Structure

```
econ-phd-advice/
├── _quarto.yml            # Main Quarto config (site title, navbar, sidebar, theme)
├── index.qmd              # Homepage / landing page
├── sections/              # One .qmd file per topic category
│   ├── undergrad.qmd      # For undergrads considering a PhD in economics
│   ├── general.qmd        # General grad school advice
│   ├── applying.qmd       # Applying to grad school
│   ├── ideas.qmd          # Finding and developing research ideas
│   ├── ideas-to-papers.qmd# From ideas to papers
│   ├── writing.qmd        # Writing advice
│   ├── presentations.qmd  # Presentation skills
│   ├── datasets-coding.qmd# Datasets and coding resources
│   ├── ai-research.qmd    # Using AI in research
│   ├── job-market.qmd     # Job market advice
│   ├── mental-health.qmd  # Mental health resources
│   ├── ra-resources.qmd   # Resources for research assistants
│   ├── conferences.qmd    # Conference listings
│   ├── funding.qmd        # Funding opportunities
│   ├── mentoring.qmd      # Mentoring programs
│   └── refereeing.qmd     # Refereeing advice
├── CONTRIBUTING.md         # Guide for community contributors
├── .github/
│   └── workflows/
│       ├── publish.yml     # Build & deploy to GitHub Pages
│       └── linkcheck.yml   # Scheduled broken-link checker
├── styles.css              # Custom CSS overrides (minimal)
└── README.md               # Repo overview for GitHub visitors
```

## Sidebar Organization

The sidebar should group pages into two logical sections to reflect the two audiences:

```yaml
# In _quarto.yml sidebar contents:
- section: "Pre-PhD"
  contents:
    - sections/undergrad.qmd
    - sections/applying.qmd

- section: "During the PhD"
  contents:
    - sections/general.qmd
    - sections/ideas.qmd
    - sections/ideas-to-papers.qmd
    - sections/writing.qmd
    - sections/presentations.qmd
    - sections/datasets-coding.qmd
    - sections/ai-research.qmd
    - sections/mental-health.qmd
    - sections/ra-resources.qmd
    - sections/conferences.qmd
    - sections/funding.qmd
    - sections/mentoring.qmd
    - sections/refereeing.qmd
    - sections/job-market.qmd
```

This keeps the undergrad page prominent and easy to find for that audience, while the bulk of the site remains PhD-focused.

## Content Format

Each section `.qmd` file follows this pattern:

```markdown
---
title: "Section Title"
---

Brief intro sentence describing what this section covers.

## Subsection (if needed)

- [Author/Title: Short description](https://link-to-resource)
  — One-line annotation explaining what the resource covers or why it's useful.
```

### Content Rules

- Every link entry is a Markdown list item: `- [Display Text](URL)`
- Add a short annotation (after ` — `) when the title alone isn't self-explanatory
- Keep annotations to one sentence
- Group related links under `##` subheadings only when a section is long enough to benefit
- Preserve all original links from the Google Sites page; mark any confirmed dead links with `<!-- DEAD LINK -->` so they can be tracked in issues
- New resources should be added at the **end** of their section (chronological ordering)

### The Undergrad Section

The `sections/undergrad.qmd` page targets undergraduates who are curious about or actively planning to pursue a PhD in economics. It should cover:

- **Deciding whether a PhD is right for you** — honest perspectives on what a PhD entails
- **Preparing your profile** — coursework (math, stats, programming), research experience, letters of recommendation
- **Pre-PhD opportunities** — RA positions, pre-doctoral programs, gap year advice
- **Mathematics preparation** — resources for building the math foundation needed for a PhD

Initial seed content comes from Aaron C. Watt's advice page (https://acwatt.net/advice/), specifically the "Advice for Undergrads" and "Mathematics" sections. Some of Watt's grad-student-focused links may duplicate resources already in other sections — that's fine, deduplicate where obvious but don't obsess over it.

This section is expected to grow significantly through community contributions since undergrad-to-PhD advice is scattered and underserved compared to the grad school advice ecosystem.

## Quarto Configuration Conventions

### `_quarto.yml`

- Use a **sidebar** navigation (not top navbar tabs) for the section pages
- Theme: `cosmo` (clean, academic feel) with minimal custom CSS
- Enable search
- Include a repo link in the navbar for easy "Edit this page" / "Report issue" flow
- Set `repo-url` and `repo-actions: [edit, issue]` so each page gets GitHub edit/issue links
- The repo URL is: `https://github.com/gjqu/econ-phd-advice`

### Styling

- Keep it minimal and professional — this is for academics
- Don't over-customize; the default Quarto theme is fine
- Use `styles.css` only for small tweaks (e.g., link list spacing)
- Include Dark Mode as a stretch goal

## Commands

```bash
# Preview locally
quarto preview

# Build the site (output to _site/)
quarto render

# Check for broken links (requires lychee CLI)
lychee --no-progress _site/**/*.html
```

## GitHub Actions

### `publish.yml`
- Triggers on push to `main`
- Installs Quarto, runs `quarto render`, deploys `_site/` to `gh-pages` branch

### `linkcheck.yml`
- Runs weekly (cron) and on-demand
- Uses `lychee` to scan all rendered HTML for broken links
- Opens an issue (or updates an existing one) with dead link report

## Contributing Guidelines (for CONTRIBUTING.md)

Contributors can:

1. **Add a resource** — Edit the relevant `sections/*.qmd` file and submit a PR
2. **Report a dead link** — Open an issue with the section name and broken URL
3. **Suggest a new section** — Open an issue for discussion before creating a PR
4. **Fix formatting / typos** — PRs welcome, no issue needed

PRs should:
- Touch only one section per PR (unless doing bulk link fixes)
- Include the URL and a one-line description for any new resource
- Not rearrange existing content without discussion

## Future Plans

- **Dashboard / visualization layer** — A future phase will add interactive visualizations of the resource collection (e.g., topic clustering, timeline of additions, most-linked domains). This will likely be a separate Quarto dashboard (`.qmd` with `format: dashboard`) or a standalone Observable/D3 page. For now, focus on clean content structure that will make this easy to build later.
- **Metadata enrichment** — We may eventually add YAML frontmatter metadata to each link (date added, tags, resource type) to power the dashboard. Design section files so this migration is straightforward.

## Important Notes

- Always verify links work before adding them
- Respect the original creators' work — this is a migration, not a rewrite
- Keep the tone welcoming — the audience now spans undergrads through senior PhD students
- When in doubt about structure, look at how the original Google Sites page organized things