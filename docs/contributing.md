# Contributing to the Hub

This document describes the small set of conventions used by Hub v0.1.

## Canonical source

Edit Hub content only in `development/hub`. The public `hub` repository is a
publication destination, not the authoritative editing location.

## Page conventions

- Use Markdown for content pages.
- Include YAML front matter with at least `title` and `nav`.
- Use the shared `default` layout supplied through `_config.yml`.
- Keep navigation labels short and consistent.
- Use descriptive link text rather than raw URLs.
- Use `relative_url` for links to pages and assets within the Hub.
- Keep placeholder functionality clearly labeled.

## Adding a page

1. Create the Markdown file in the Hub root unless a subdirectory is justified.
2. Add front matter.
3. Add the page to `_layouts/default.html` only if it belongs in primary
   navigation.
4. Check the page at narrow and wide viewport widths.
5. Validate all local and external links.

## Adding a module to the catalog

Add a module card to `modules.md` only after its public repository exists. Each
entry should include:

- module title;
- concise description;
- development status when useful;
- public repository link;
- browser notebook link or a clearly labeled status note.

Never link to private instructor repositories from the public catalog.

## Styling

Shared styles live in `assets/css/style.css`. Reuse the existing layout classes
before introducing new ones. Keep the site dependency-light and avoid
JavaScript unless a future requirement clearly justifies it.

## Publication check

Run a dry publication before copying files:

```bash
python scripts/publish.py --target hub --dry-run --verbose
```

Review copied, updated, unchanged, skipped, and invalid files. Publish only when
the report is correct. Then inspect the destination repository in GitHub
Desktop before committing.
