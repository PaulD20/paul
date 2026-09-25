# Evaluation report

Answer concisely in your own words. Refer to concrete evidence from the project
and its tools.

## 1. Initial assessment

What was incomplete, incorrectly configured, or failing when you first examined
the repository? Explain how you discovered each item.

a list of issues, with the command that revealed each one. For example:
- ruff, mypy, and pytest missing from `pyproject.toml` → spotted while reading the file, and `uv run pytest` failed
- no README or LICENSE → spotted using `ls -a`
- 3 failing tests → spotted using `uv run pytest`

## 2. Toolchain evidence

What did the quality chain tools contribute to
your investigation? Give relevant examples and distinguish the kinds of
problems they can detect.

Each tool showing that each detects a different type of problem:

- ruff format → formatting (spaces, quotation marks)
- ruff check → errors detectable without executing the code (unused imports, unused variables)
- mypy → type inconsistencies (a function expected to return a `float` returning something else)
- pytest → actual behavior, calculation yielding an incorrect result



## 3. Corrections

Describe the implementation and configuration corrections you made. For each
important correction, connect the original problem, the evidence, and the
resulting behavior.
 
 For the test_metrics.py expected 5.0 and received 0.05 so the function was not multiplying by 100 but i didn't succed to fix it so test does not pass



## 4. Reproducibility and local configuration

Explain how the completed repository lets another developer reconstruct,
configure, run, and verify the project safely.

- `pyproject.toml` declares dependencies, and `uv.lock` locks the exact versions. Consequently, `uv sync` recreates the same environment for anyone.
- `.env` contains the actual token; it is **not** version-controlled and is listed in `.gitignore`.
- `.env.example` doesn't work (or i don't know what it is supposed to do)
- The README provides the commands for installation, configuration, execution, and verification.

## 5. Git workflow

Explain how your branches and commits divide the work into reviewable changes.
Mention how the completed work was integrated.

I didn't succed to create feature branches because if i did this, i lost my main branch that i initialize with `git init -b main`

## 6. Limits of verification

Why does a completely passing quality toolchain provide useful evidence but not
proof that the program contains no defects?

## 7. Bonus question

Document the investigation trail for the bonus question:

1. How did you decide which project tool was responsible for this type of
   policy?
2. What documentation or repository evidence did you consult?
3. Which rule or rule family did you identify, and what behavior does it check?
4. What configuration did you change, and how did you verify that every existing
   rule remained enabled?
5. What new diagnostic appeared after the configuration change?
