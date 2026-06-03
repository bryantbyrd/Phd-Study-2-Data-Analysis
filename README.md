# Study 2: IPC vs. Sham — Exercise Performance and Blood Lactate

This repository contains all analysis notebooks for Study 2, which examines the effects of ischemic preconditioning (IPC) versus sham treatment on exercise performance outcomes and blood lactate responses.

## Files

| File | Language | Description |
|---|---|---|
| `Study_2_Statistics.ipynb` | R | All inferential statistics: ANCOVA for performance outcomes, linear mixed model for lactate, model diagnostics |
| `Lactate_Figure.ipynb` | Python | 2-panel lactate response figure (Baseline vs. Trial) and descriptive statistics table |

> **Note:** Statistics are in R and figures are in Python — both notebooks were originally developed in Google Colab. Colab-specific calls have been removed so the notebooks run in any standard environment.

## Data

Place the required data file in a `data/` folder before running either notebook:

```
data/
  Spreadsheet_Study_2.xlsx
```

Data files are not included in this repository. Please contact the authors for access.

## Participant Exclusion

Subject **Brian** was excluded from all analyses.

## Analyses

### `Study_2_Statistics.ipynb`
- **ANCOVA — 3600 m**: Post-trial time adjusted for baseline (IPC vs. Sham)
- **ANCOVA — 1200 m**: Post-trial time adjusted for baseline (IPC vs. Sham)
- **ANCOVA — Critical Speed**: Post-trial critical speed adjusted for baseline
- **ANCOVA — D′**: Post-trial anaerobic work capacity adjusted for baseline
- **Lactate LME**: Three-way mixed model (group × visit × timepoint) on log-transformed lactate; difference-in-differences contrasts with BH correction
- **Diagnostics**: Residual plots, Cook's distance, leverage, NCV test, DHARMa simulation check

### `Lactate_Figure.ipynb`
- 2-panel figure: mean ± SD lactate for IPC vs. Sham across timepoints (Panel A: Baseline, Panel B: Trial)
- Descriptive statistics table (Mean ± SD) by group and visit

## R Packages Required

```r
install.packages(c(
  "tidyverse", "readxl", "lme4", "lmerTest",
  "emmeans", "broom", "car", "DHARMa"
))
```

## Python Packages Required

```bash
pip install pandas matplotlib seaborn openpyxl
```

## Running the Notebooks

Open in JupyterLab, Jupyter Notebook, VS Code, or Google Colab (re-add `drive.mount()` if using Colab):

```bash
jupyter notebook Study_2_Statistics.ipynb
```
