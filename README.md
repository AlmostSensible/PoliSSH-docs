# PoliSSH documentation

Public Polish and English user documentation. The application code is maintained separately in a private repository.

**Website:** https://almostsensible.github.io/PoliSSH-docs/

## Local preview

```sh
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

Open http://127.0.0.1:8000. Before publishing, run `mkdocs build --strict`.

## Updating documentation

Edit Markdown in `docs/`; keep Polish and English descriptions aligned. Use fictional hosts in examples and screenshots. Mark features that are unavailable in released builds as Unreleased / Niewydane. Do not copy application source, credentials or private operational notes here.

Pushes to `main` build and deploy automatically through GitHub Actions. Pull requests run a build check without deployment. GitHub Pages uses the GitHub Actions publishing source. An environment approval may be required if configured by the organization.

The original documentation-only PR in the application repository is maintained independently; this site does not automatically copy that private repository.
