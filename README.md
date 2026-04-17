# notification-docs

Documentation for the partner notification platform: onboarding, notification setup, authentication, and technical discovery flows.

## Browse locally

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
mkdocs serve
```

Open the URL printed in the terminal (usually `http://127.0.0.1:8000/`).

## GitHub Pages (automatic)

**Published site:** [https://sydlab.github.io/notification-docs/](https://sydlab.github.io/notification-docs/)

The workflow [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml) builds the site with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) on every push to `main` (and on manual **Run workflow**). It deploys to the repository’s default GitHub Pages URL (above assumes the GitHub repository is named `notification-docs`). The workflow does not hardcode a hostname; canonical links and the “edit on GitHub” targets come from [`mkdocs.yml`](mkdocs.yml) (`site_url`, `repo_url`, `repo_name`).

1. In the GitHub repository, go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **GitHub Actions** (not “Deploy from a branch”).
3. If you fork this repo or change the Pages URL, update `site_url`, `repo_url`, and `repo_name` in [`mkdocs.yml`](mkdocs.yml) so search, sitemaps, and repo links stay correct.
4. Push to `main`. The **Deploy documentation to GitHub Pages** workflow should publish the `site/` output.

## Layout

| Path | Purpose |
|------|---------|
| [`docs/`](docs/index.md) | Source Markdown for the published site |
| [`docs/technical-flows/`](docs/technical-flows/index.md) | Discovery flows: `.mmd` sources plus wrapper pages that render them |
| [`mkdocs.yml`](mkdocs.yml) | Site name, nav, theme, Mermaid / snippets |

Later steps can add an `docs/architecture/` area for AWS (EKS, Secrets Manager, Aurora PostgreSQL, event-driven design) without changing this layout.
