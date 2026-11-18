# Stack: python

Detect: `pyproject.toml`, `requirements.txt` or `setup.py`. Assumes the `src/` layout.

- **Versions**: the Python version from `pyproject.toml`, otherwise ask.
- **Test command**: `uv run pytest` if the project uses uv, otherwise `pytest`. One file: `pytest <path>`.
- **Test framework**: pytest.
- **Docs**: https://docs.python.org/3/ , https://docs.pytest.org/

| Type | Hers, edits denied | Open to AI |
|---|---|---|
| exercises | `src/` | `tests/exercises/` for exercise tests, `tests/data/` for test data |
| portfolio | `src/`, `tests/` | `dev/` for fakes, stubs, data generators and seeds, `fixtures/` for data files |
