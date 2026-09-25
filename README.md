Campaign Validator is a small Python command-line application for checking advertising campaign data. It normalizes a campaign name, calculates a click-through-rate percentage, counts campaign tags, and verifies that the local campaign access token is configured correctly.


### 1. Recreate the Python environment

After cloning the repository, enter the project directory:

```
cd evaluation-python-test-main
```

Then run:

```
uv sync --locked
```

This uses `pyproject.toml` and `uv.lock` to recreate the project's Python environment and install its dependencies. The `--locked` option makes sure that `uv` uses the existing `uv.lock` file without changing it.

### 2. Create the local `.env` file

Create a `.env` file from the example:

```
cp .env.example .env
```

Open `.env` and add the required local configuration values.

The `.env` file is local to the machine and may contain secrets, so it must not be committed to Git.

### 3. Run the application

Run the application through `uv` so that it uses the project's environment:

```
uv run <application-command>
```

Replace `<application-command>` with the command defined by the project.

### 4. Run the quality checks

Before committing changes, run the project's quality checks:

```
uv run ruff check .
uv run ruff format --check .
uv run mypy .
uv run pytest
```

These commands check the code for linting problems, formatting problems, type errors, and failing tests.

If all checks pass, the code is ready to be committed.