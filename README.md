# CROSSROADS Hub

This directory is the canonical Hub source inside the private `development`
repository. Approved files are published to the public `hub` repository using
the CROSSROADS Publication Tool.

## Hub v0.1

The initial Hub provides:

- a public landing page;
- project and platform background;
- a module catalog;
- concise educator guidance;
- links to the Forum and GitHub organization;
- a responsive, dependency-light Jekyll layout.

## Structure

```text
hub/
├── README.md
├── _config.yml
├── _layouts/
│   └── default.html
├── index.md
├── about.md
├── modules.md
├── educators.md
├── assets/
│   └── css/
│       └── style.css
└── docs/
    └── contributing.md
```

## Editing pages

Each public page is a Markdown file with YAML front matter. Preserve the
`title` and `nav` values so the shared layout can generate page titles and
indicate the active navigation item.

Internal Hub links should use Jekyll's `relative_url` filter so the site works
when GitHub Pages serves it from the `/hub` project path.

## Adding a module

1. Confirm that the public module repository exists.
2. Add a module card to `modules.md`.
3. Include a title, short description, repository link, and notebook status or
   link.
4. Do not link instructor-only materials from the public Hub.
5. Validate links before publication.

More detailed guidance is in [`docs/contributing.md`](docs/contributing.md).

## Local preview

The site uses standard Jekyll features supported by GitHub Pages. In a local
Jekyll environment, run the site from this directory with the repository's
preferred Jekyll command and preview it at the local address reported by
Jekyll.

The site does not require a remote theme or JavaScript framework.

## Publication

From the `development` repository, preview publication first:

```bash
python scripts/publish.py --target hub --dry-run --verbose
```

After reviewing the report, publish the approved files:

```bash
python scripts/publish.py --target hub
```

The Publication Tool performs no Git operations. Review the resulting changes
in the public `hub` repository before committing and pushing them.

## GitHub Pages

Configure GitHub Pages in the public `hub` repository to deploy from the branch
and folder selected by project leadership. Hub v0.1 is designed for GitHub
Pages' standard Jekyll build and does not require a custom GitHub Actions
workflow.
