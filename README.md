🌐 [Português (BR)](README.pt_BR.md) · [Español](README.es.md)

# 🎉 Soc Ops

**Turn “Hi, what do you do?” into a game.** Soc Ops is social bingo for in-person
mixers: find people who match the prompts, mark your squares, and get five in a row.

**[Start the Copilot Agent Lab →](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview)**
· [Run the game locally](#-run-it-locally) · [Explore the workshop](#-learn-by-building)

## 🤝 Break the ice, one square at a time

1. Start a game and scan the bingo board.
2. Find someone who matches a square and tap it.
3. Keep meeting people until you get **five in a row** — BINGO!

## 🧪 Learn by building

Build Soc Ops while exploring GitHub Copilot Agent Mode, from project context and
design-first development to custom agents and multi-agent workflows. The guided lab
takes about an hour, with an online guide and offline materials:

| Part | Explore |
|------|---------|
| [**00 · Overview**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview) | Get oriented and check the prerequisites |
| [**01 · Setup**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=01-setup) | Set up the project and engineer context |
| [**02 · Design**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=02-design) | Create a design-first frontend |
| [**03 · Quiz Master**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=03-quiz-master) | Make a custom agent for themed prompts |
| [**04 · Multi-Agent**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=04-multi-agent) | Build features with multiple agents |

> Prefer to read offline? The same lab guides are in [`workshop/`](workshop/).

## 🚀 Run it locally

You’ll need [Python 3.13+](https://www.python.org/) and [`uv`](https://docs.astral.sh/uv/).

```bash
uv sync
uv run uvicorn app.main:app --reload
```

Open [http://localhost:8000](http://localhost:8000) and start meeting your squares.

## Deploy the workshop to GitHub Pages

Before running `.github/workflows/deploy.yml` in your repository, an owner or
maintainer must open **Settings → Pages → Build and deployment** and select
**GitHub Actions** as the **Source**. The workflow's `GITHUB_TOKEN` can deploy to
an existing Pages site, but cannot enable Pages automatically.

If `build-and-deploy` fails at **Configure GitHub Pages** with
`Get Pages site failed` / `HttpError: Not Found`, configure this setting, then
rerun the failed workflow from the **Actions** tab. No code change or additional
token is needed to enable deployment once Pages is configured.

GitHub Pages hosts the static workshop and start-screen preview only; run the
FastAPI server locally for the interactive game.

---

Built with Python, FastAPI, and HTMX. Have fun, meet someone new, and call **BINGO!**

## Code Quality

Run `uv run ruff check .` to check code style, unused imports and variables (`F`),
unused arguments (`ARG`), and function type annotations (`ANN`). Ruff enforces
annotation presence, not type correctness. Historical workshop checkpoints in
`.solutions/` are excluded from root-level linting.
Run `uv run python -m compileall -q app` to check compilation and `uv run pytest`
to run the tests.
to run the tests.
