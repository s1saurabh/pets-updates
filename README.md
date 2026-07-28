# Flask Pets Workshop: Full-Stack Python Web App + GitHub Developer Workshop

**Flask workshop** and **GitHub hands-on lab** built around a fictional dog shelter (**Pets**). Learn **Flask + SQLAlchemy** backend and **Astro + Svelte** frontend while practicing **GitHub Copilot, Issues, Codespaces, testing, and deployment** workflows.

> **Lab 2** in the [Python learning path](https://github.com/saurabhahuja71/learning-path#2-python--data--apis) · Audience: beginners → intermediate · Time: 1 hour or full day · Level: intermediate beginner

## What is this repository?

Two guided workshops on one product codebase:

| Workshop | Path | Focus |
|----------|------|--------|
| **1-hour** | [`content/1-hour/`](./content/1-hour/README.md) | GitHub Copilot productivity |
| **Full-day** | [`content/full-day/`](./content/full-day/README.md) | Day-in-the-life DevOps on GitHub |

Application stack:

- **Backend:** [Flask](https://flask.palletsprojects.com/) + [SQLAlchemy](https://www.sqlalchemy.org/)
- **Frontend:** [Astro](https://astro.build/) + [Svelte](https://svelte.dev/)

**SEO keywords:** *Flask workshop for beginners*, *GitHub Copilot workshop*, *Flask SQLAlchemy example*, *Astro Svelte Python full stack*, *college Flask project*, *GitHub Codespaces tutorial*, *pets shelter demo app*.

## Why students like this lab

- Realistic product story (not only CRUD snippets)
- Curriculum content under `content/` (setup → features → deploy)
- Practices modern GitHub workflows used in industry
- MIT licensed, contribution-friendly

## Prerequisites

- GitHub account
- Python 3.10+ and Node.js (for local full stack)
- Optional: GitHub Codespaces (easiest classroom path)
- Comfortable with Lab 1 API concepts: [react-fastapi-todo](https://github.com/saurabhahuja71/react-fastapi-todo)

## Quick start (choose a workshop)

```bash
git clone https://github.com/saurabhahuja71/pets-updates.git
cd pets-updates
```

1. Open the **content index**: [`content/README.md`](./content/README.md)  
2. Pick **1-hour** or **full-day**  
3. Follow step files (`0-setup.md`, `1-…`, …)

### Project layout (high level)

```text
pets-updates/
├── client/          # Astro + Svelte frontend
├── server/          # Flask backend (see repo)
├── content/         # Workshop lessons
│   ├── 1-hour/
│   └── full-day/
├── scripts/
└── README.md
```

Exact run commands live in the workshop markdown (they stay accurate as the app evolves).

## What you will practice

- Exploring a multi-package monorepo  
- Adding an API endpoint / feature with guided prompts  
- Using Issues, PR flow, code scanning concepts  
- Testing and deployment sections (full-day track)  
- Responsible use of **GitHub Copilot** for learning (not blind copy)

## Lab exercises (after the official workshop)

1. Add a new pet field and show it on the UI.  
2. Write one backend unit test for a service function.  
3. Document your feature in a PR description like a real team.  
4. Compare Flask routing here with FastAPI in Lab 1.  
5. Stretch: containerize `server` + `client` with Compose.

## Learning path

| # | Lab | Focus |
|---|-----|--------|
| 1 | [react-fastapi-todo](https://github.com/saurabhahuja71/react-fastapi-todo) | FastAPI full stack |
| **2 (this)** | pets-updates | Flask product + GitHub workshop |
| 3 | [sample-regression-model](https://github.com/saurabhahuja71/sample-regression-model) | ML regression intro |

Hub: [learning-path](https://github.com/saurabhahuja71/learning-path)

## Community & support

- [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)  
- [CONTRIBUTING.md](./CONTRIBUTING.md)  
- [SECURITY.md](./SECURITY.md)  
- Maintainers: [CODEOWNERS](./.github/CODEOWNERS)

## FAQ — Flask & GitHub workshops

**Do I need Copilot paid access?**  
The 1-hour track is Copilot-focused; full-day still teaches GitHub flow without every step requiring Copilot.

**Is this only for dog apps?**  
The domain is fictional shelter software — patterns apply to any CRUD + content site.

**Flask or FastAPI first?**  
Either order works. FastAPI emphasizes OpenAPI; Flask is ubiquitous in tutorials and older codebases.

## Topics / SEO tags

`flask` `sqlalchemy` `python` `astro` `svelte` `github-copilot` `workshop` `codespaces` `devops` `tutorial` `fullstack` `college` `education`

## Maintainers

See [CODEOWNERS](./.github/CODEOWNERS). Educational packaging and SEO README curated for the [learning-path](https://github.com/saurabhahuja71/learning-path) hub by [Saurabh Ahuja](https://github.com/saurabhahuja71).

## License

MIT — see [LICENSE](./LICENSE) / project license files.
