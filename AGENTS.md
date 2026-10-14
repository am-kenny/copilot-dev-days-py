# Mandatory Development Checklist

Before considering an implementation change complete, run all three checks:

- [ ] Lint: `uv run ruff check .`
- [ ] Build/compile check: `uv run python -m compileall -q app`
- [ ] Test: `uv run pytest`

# Repository Guide

Soc Ops is a FastAPI social bingo app. Keep changes within the existing boundaries:

- `app/game_logic.py` owns board generation, square toggling, and bingo rules; `app/game_service.py` owns per-game state.
- `app/main.py` wires routes and sessions. Keep route behavior aligned with the Jinja templates in `app/templates/` and their HTMX targets/fragments.
- `app/models.py` and `app/data.py` define square/line data and the question pool.
- The game uses a 5x5 board with a non-toggleable free center. Session state is held in an in-memory registry, so it is not shared across worker processes or preserved across restarts.

## Verify Changes

- Tests: `uv run pytest`
- Lint: `uv run ruff check .`
- Run locally: `uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000`

Route and rendered-response coverage is in `tests/test_api.py`; game-rule coverage is in `tests/test_game_logic.py`.

## UI Conventions

- Use the project-defined CSS utilities in `app/static/css/app.css`; there is no Tailwind dependency. See [CSS utility guidance](.github/instructions/css-utilities.instructions.md).
- Follow [frontend design guidance](.github/instructions/frontend-design.instructions.md) for UI work.
- Keep server-rendered fragments and their HTMX swap targets in sync when changing interactions.

## Project References

- [README](README.md) links to the lab and setup overview.
- [Workshop guide](workshop/GUIDE.md) and [workshop overview](workshop/00-overview.md) contain the hands-on workshop material; link there rather than duplicating it.