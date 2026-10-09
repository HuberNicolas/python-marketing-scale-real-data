<div align="center">

# Python for Marketing

**Coursework for Python – A non-technical introduction with applications to Marketing, University of Zurich, Fall 2023**

![Python](https://img.shields.io/badge/Python-3.9-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-2.0-150458?logo=pandas&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?logo=sqlite&logoColor=white)
![uv](https://img.shields.io/badge/uv-DE5FE9?logo=uv&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow)

[Contents](#contents) · [Getting started](#getting-started) · [Data](#data) · [Release as submitted](https://github.com/HuberNicolas/python-marketing-scale-real-data/releases/tag/v1.0.0)

</div>

My exercise notebooks from a five-day block course on Python for data analysis in marketing. The exercises work with
the transactions and demographics of a retailer's customers: loading and plotting data, selecting, aggregating and
merging it with pandas and SQL, conditions, loops and functions, simulating data, and finally an RFM (recency,
frequency, monetary value) customer scoring model with an in-class Kaggle competition.

> [!NOTE]
> This is unofficial study material. The notebooks are shown as I worked on them in August 2023: they are not
> corrected, and the repository is not developed further. The lecture notebooks, exercise templates, official
> solutions and the course data are not included. The library versions are pinned to September 2023.

## Contents

| Day | Session | Topic | Notebook |
|---|---|---|---|
| 1 | 1 | Getting started: code notebooks, a local editor, packages, getting help | [Session 1](day-1/Python_Day_1_Session_1_Exercise.ipynb) |
| 1 | 2 | Reading data and a first look at it | [Session 2](day-1/Python_Day_1_Session_2_Exercise.ipynb) |
| 1 | 3 | Basic plots with Matplotlib | [Session 3](day-1/Python_Day_1_Session_3_Exercise.ipynb) |
| 2 | 1 | Advanced plots, colour palettes and themes with seaborn | [Session 1](day-2/Python_Day_2_Session_1_Exercise.ipynb) |
| 2 | 2 | Selecting, appending and updating rows and columns | [Session 2](day-2/Python_Day_2_Session_2_Exercise.ipynb) |
| 2 | 3 | Aggregating data | [Session 3](day-2/Python_Day_2_Session_3_Exercise.ipynb) |
| 3 | 1 | Merging data: inner, outer, left and right joins | [Session 1](day-3/Python_Day_3_Session_1_Exercise.ipynb) |
| 3 | 2 | Connecting to a database, the role of SQL | [Session 2](day-3/Python_Day_3_Session_2_Exercise.ipynb) |
| 3 | 3 | Select, aggregate and merge operations in SQL | [Session 3](day-3/Python_Day_3_Session_3_Exercise.ipynb) |
| 4 | 1 | Conditions and loops | [Session 1](day-4/Python_Day_4_Session_1_Exercise.ipynb) |
| 4 | 2 | Functions | [Session 2](day-4/Python_Day_4_Session_2_Exercise.ipynb) |
| 4 | 3 | Simulating sequences, strings and variables | [Session 3](day-4/Python_Day_4_Session_3_Exercise.ipynb) |
| 5 | – | Final exercise: RFM scoring model and Kaggle competition | [RFM + Kaggle](day-5/Python_Day_5_RFM+Kaggle.ipynb) |

The notebooks were started in Google Colab and later run locally in Jupyter.

## Getting started

You need [uv](https://docs.astral.sh/uv/). It installs Python 3.9 and the pinned libraries from `uv.lock`.

1. Clone the repository:

   ```bash
   git clone https://github.com/HuberNicolas/python-marketing-scale-real-data.git
   ```

   ```bash
   cd python-marketing-scale-real-data
   ```

2. Install the environment:

   ```bash
   uv sync
   ```

3. Download the SQLite database for day 3. The notebooks call `wget`, which is not installed on every system, and
   session 3 opens the file as `database1.sqlite`:

   ```bash
   curl -L -o day-3/database.sqlite https://raw.githubusercontent.com/bachmannpatrick/Python-Class/master/data/database.sqlite
   ```

   ```bash
   cp day-3/database.sqlite day-3/database1.sqlite
   ```

4. Start Jupyter and open a notebook from the table above. Run it from its own folder:

   ```bash
   uv run jupyter notebook
   ```

### Tech stack

| Area | Libraries |
|---|---|
| Data | ![pandas](https://img.shields.io/badge/pandas-2.0.3-150458?logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-1.25.2-013243?logo=numpy&logoColor=white) ![SQLite](https://img.shields.io/badge/SQLite-003B57?logo=sqlite&logoColor=white) |
| Plots | ![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7.2-11557C) ![seaborn](https://img.shields.io/badge/seaborn-0.12-4C72B0) |
| Notebooks | ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white) ![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?logo=googlecolab&logoColor=white) |

pandas, NumPy and Matplotlib are pinned to the versions that `pip list` shows in the day 1 notebook. `pyproject.toml`
resolves all other libraries as of 5 September 2023 (`exclude-newer`). Day 4 uses the
[`names`](https://pypi.org/project/names/) package to generate random person names.

## Data

The notebooks load the course data directly from GitHub, so it is not part of this repository.

| Data | Used in | Source |
|---|---|---|
| `transactions.csv`, `demographics.csv`: transactions and demographics of a retailer's customers | Days 1–5 | [bachmannpatrick/Python-Class](https://github.com/bachmannpatrick/Python-Class/tree/master/data), the data repository of the course |
| `database.sqlite`: the same two tables as a SQLite database | Day 3 | Same repository |
| `training_data.csv`, `sample_submission.csv` | Day 5, task 7 | The in-class Kaggle competition; not public |

The data repository has no license, so the data is not redistributed here.

## Known issues

- Day 5, task 7 needs `training_data.csv` from the in-class Kaggle competition, which is not available. The cells
  before it run.
- Day 5 contains errors as submitted: `calculateRFMscores()` is called with an argument it does not accept, one cell
  fails on `iloc` with a boolean mask, and some cells were never run (one of them has a syntax error).
- The notebooks were run with Python 3.11 (day 1) and 3.9 (days 2–5). The shared environment uses Python 3.9; all
  notebooks except day 5 run in it without errors (checked in October 2026).
- Answers may be wrong or incomplete in places. They are left as I wrote them.

## Author

Nicolas Huber ([@HuberNicolas](https://github.com/HuberNicolas)), Master's student at the University of Zurich.

## Acknowledgements

The block course Python – A non-technical introduction with applications to Marketing (3 ECTS, Fall 2023) was
offered by the [Chair of Marketing for Social Impact](https://business.uzh.ch/de/research/professorships/market-research/education/Curriculum/Fall-Semester-Courses/Python-N-non-technical-introduction.html),
Department of Business Administration, University of Zurich. The exercise tasks quoted in the notebooks and the data
come from the course.

## License

The notebooks are licensed under the [MIT License](LICENSE). The data and the exercise texts quoted in the notebooks
belong to their respective owners.
