# Contributing

This site is community-maintained. Whether you're a first-year PhD student or a tenured professor, your contributions help everyone. Here's how to help.

## Add a resource

1. Find the right file in `sections/` (e.g., `sections/writing.qmd` for writing advice).
2. Add your link at the **end** of the section using this format:

   ```markdown
   - [Author: Title](https://url)
     — One-line description if the title isn't self-explanatory.
   ```

3. Open a pull request. One section per PR keeps reviews fast.

## Report a dead link

Open an [issue](https://github.com/gjqu/econ-phd-advice/issues) with the section name and the broken URL. We'll fix or remove it.

## Suggest a new section

Open an issue first so we can discuss where it fits before you write anything.

## Fix typos or formatting

PRs welcome — no issue needed.

## PR guidelines

- Touch only one section per PR (unless doing bulk link fixes)
- Include the URL and a one-line description for any new resource
- Verify your links work before submitting
- Don't rearrange existing content without discussion

## Local preview

```bash
quarto preview
```

Requires [Quarto](https://quarto.org/) >= 1.4.
