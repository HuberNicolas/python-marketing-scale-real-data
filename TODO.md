# TODO

Open tasks for this repository. See also [Known issues](README.md#known-issues).

## 1. Clean-up

- [x] Tag the submitted state as `v1.0.0` (commit "Kaggle", 4 September 2023)
- [x] Remove the lecture notebooks, exercise templates and official solutions from the current state (they stay in old commits)
- [x] Remove the course data (SQLite database twice, Kaggle archive); the notebooks download the data themselves

## 2. Environment

- [x] Add `pyproject.toml` and `uv.lock` with Python 3.9 and the library versions of the course
- [x] Run all notebooks in a copy: days 1–4 run without errors; day 5 fails as submitted (see Known issues)

## 3. Documentation

- [x] Rewrite the README (contents per session, data, known issues)
- [ ] Add the names of the 2023 instructors to the Acknowledgements (the course page only lists the current ones)

## 4. Before publishing

- [x] Choose and add a license (MIT)
- [x] Check for secrets in the files and the git history (9 October 2026: nothing found)
- [x] Rewrite the old commit e-mail address with a mailmap (dates and content stay the same)
- [ ] Rename the GitHub repository to `python-marketing-uzh`, then update the remote and the links in the README
- [ ] Push `main` and the tags, create the releases `v1.0.0` (as submitted) and `v1.1.0` (cleaned up)
