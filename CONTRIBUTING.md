# Contributing

Thanks for your interest in making this resource better! This site is
community-maintained, and contributions from anyone — undergrads, PhD students,
postdocs, faculty — are welcome and appreciated.

No contribution is too small. A single useful link you've found can help
hundreds of students.

## Ways to contribute

The best way to contribute is to **open a pull request**. We strongly recommend
working locally — clone the repo, create a branch, preview your changes with
`quarto preview`, and submit a PR from there. This lets you verify everything
looks right before anyone else sees it, and it keeps the review process smooth.

See the [local workflow](#local-workflow-recommended) section below for the
full steps.

### Report a broken link

Found a link that no longer works? Open an
[issue](https://github.com/gjqu/econ-phd-advice/issues/new) with:

- **Title:** "Broken link in [section name]"
- **Body:** the broken URL and, if you know of one, a replacement link

We'll fix or remove it.

### Suggest a new resource

If you know a great resource that belongs on this site, you can either:

- **Quick way:** open an [issue](https://github.com/gjqu/econ-phd-advice/issues/new)
  with the link, a short description, and which section it belongs in. We'll
  add it for you.
- **DIY way:** edit the relevant `.qmd` file and submit a pull request (see the
  step-by-step guide below).

### Suggest a new section

If you think the site is missing an entire topic area, open an
[issue](https://github.com/gjqu/econ-phd-advice/issues/new) so we can discuss
where it fits before anyone starts writing.

### Fix typos or formatting

Pull requests for small fixes are always welcome — no issue needed.

## Development setup

1. Install [Quarto](https://quarto.org/docs/get-started/) (>= 1.4)
2. Clone the repo and run `quarto preview` to start a local dev server
3. Edit any `.qmd` file — the preview hot-reloads on save
4. (Optional) Install [lychee](https://github.com/lycheeverse/lychee) to check for broken links: `lychee _site/**/*.html`

## How to submit a pull request

### Local workflow (recommended)

Working locally lets you preview exactly how your changes will look on the site
before submitting. Requires [Quarto](https://quarto.org/) >= 1.4.

```bash
# 1. Fork and clone the repo
git clone https://github.com/<your-username>/econ-phd-advice.git
cd econ-phd-advice

# 2. Create a branch for your changes
git checkout -b add-writing-resource

# 3. Preview the site locally
quarto preview

# 4. Edit the relevant .qmd file in sections/
#    (the preview will hot-reload as you save)

# 5. Commit and push
git add sections/writing.qmd
git commit -m "Add Cochrane's writing tips to writing section"
git push -u origin add-writing-resource
```

Then open a pull request on GitHub from your branch. We'll review and merge it —
if we have questions, we'll leave a comment on the PR.

### Via GitHub's web interface

For quick, small edits you can also use GitHub directly:

1. Navigate to the file in
   [`sections/`](https://github.com/gjqu/econ-phd-advice/tree/main/sections)
   and click the pencil icon to edit.
2. Make your changes, write a short commit message, and click **"Propose
   changes"**.
3. Click **"Create pull request"** on the next page and submit.

This works fine for adding a single link, but you won't be able to preview how
the page renders — so for anything beyond a one-liner, the local workflow is
preferred.

## Content formatting guidelines

Every resource should be a Markdown list item in this format:

```markdown
- [Author or Source: Title of Resource](https://url)
  — One-line description if the title alone isn't self-explanatory.
```

A few rules:

- **Add new links at the end** of their section (this keeps a rough
  chronological ordering).
- **Keep annotations to one sentence.** They should explain *why* the resource
  is useful, not summarize its entire contents.
- **Skip the annotation** if the title is already clear
  (e.g., "Jesse Shapiro: How to Give an Applied Micro Talk" doesn't need
  further explanation).
- **Verify your links work** before submitting.
- **One section per PR** unless you're doing a bulk fix across sections.
- **Don't rearrange existing content** without opening an issue for discussion
  first.

## Where contributions are most needed

The **[undergrad section](sections/undergrad.qmd)** is especially in need of
contributions. Advice for undergrads considering an econ PhD is scattered
across the internet and underserved compared to the grad school advice
ecosystem. If you know of resources on:

- Pre-doctoral programs and RA positions (NBER, Fed, J-PAL, IPA, etc.)
- Deciding whether a PhD is right for you
- Building an application profile as an undergrad
- Math preparation for economics

...please consider adding them!

## Code of conduct

This project follows the
[Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/).
Be kind, be constructive, and keep the focus on helping students.
