# Repository Guidelines

## Project Structure & Module Organization

- `src/artisan.py` is the main entry point; core logic lives in `src/artisanlib/`.
- `src/plus/` contains artisan.plus features; `src/help/` includes help dialog sources.
- UI assets and templates are under `src/includes/` (icons, themes, HTML templates).
- Tests live in `src/test/` with fixtures and data under `src/test/data/` and `src/test/sanity/data/`.
- Documentation is split between `README.md`, `CONTRIBUTING.md`, `wiki/`, and `doc/`.

## Build, Test, and Development Commands

Run commands from `src/` unless noted.

- `python3 -m venv artisan_venv` and `source artisan_venv/bin/activate` to set up a venv.
- `pip install -r requirements.txt` to install runtime dependencies.
- `python3 artisan.py` to run the application locally.
- `pip install -r requirements-dev.txt` to install dev tooling.
- `codespell` to run spell checks.
- `ruff check .` and `pylint */*.py` for linting (see `src/pyproject.toml`).
- `mypy` and `pyright` for type checking.
- `pytest` for the test suite.

## Coding Style & Naming Conventions

- Python code follows Black with `line-length = 100` (`src/pyproject.toml`).
- Linting uses Ruff and Pylint; type checking uses MyPy and Pyright.
- Keep module and function names descriptive; follow existing patterns in `src/artisanlib/`.

## Testing Guidelines

- Pytest is configured via `src/pyproject.toml` (`testpaths = ["test"]`).
- Test files follow `test_*.py` naming in `src/test/` (unitary, sanity, smoke, uat).
- Add or update fixtures in `src/test/data/` when introducing new parsing or import logic.

## Commit & Pull Request Guidelines

- Commit messages in history are short summaries (often imperative); multi-change commits sometimes use a follow-up list in the body. Keep the subject concise.
- PRs should include a clear description, link related issues, and enable maintainer edits.
- Expect review feedback and update your branch as requested (see `CONTRIBUTING.md`).

## Notes

- CI builds are handled by GitHub Actions and AppVeyor; local packaging is not supported without repo changes (see `wiki/HowToBuildArtisan.md`).
