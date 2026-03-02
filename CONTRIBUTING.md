# Contributing

Thanks for your interest in making this resource better! This site is
community-maintained, and contributions from anyone — undergrads, PhD students,
postdocs, faculty — are welcome and appreciated.

No contribution is too small. A single useful link you've found can help
hundreds of students.

## Ways to contribute

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

## How to submit a pull request (step by step)

Here's how to add a resource using GitHub's web interface — no command line required.

1. **Find the right file.** Section files live in the
   [`sections/`](https://github.com/gjqu/econ-phd-advice/tree/main/sections)
   folder. Click into the one you want to edit (e.g., `writing.qmd` for writing
   advice).

2. **Click the pencil icon** (top right of the file view) to edit the file.
   GitHub will automatically create a "fork" (your own copy of the project) if
   you don't have one yet.

3. **Add your resource** at the end of the relevant section, using the
   formatting guidelines below.

4. **Scroll down** and write a short commit message describing what you added
   (e.g., "Add Cochrane's writing tips to writing section").

5. **Click "Propose changes"**, then **"Create pull request"** on the next page.
   Add a brief description if you like, then submit.

That's it! We'll review your PR and merge it if everything looks good. If we
have questions, we'll leave a comment on the PR.

### If you prefer working locally

```bash
# Fork and clone the repo, then:
quarto preview        # preview the site at localhost
# Make your edits, then commit and push
```

Requires [Quarto](https://quarto.org/) >= 1.4.

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
