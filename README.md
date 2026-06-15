# Accelerated Stability Study — Formulation A vs B

Analysis for the KTP Associate pre-interview data exercise. A single Jupyter
notebook works through the six questions in the brief on an accelerated
stability dataset comparing two prototype formulations (Lot A014 and Lot B025).

## Headline findings

- The study is a **paired** design: 19 identical (temperature, %RH, exposure)
  conditions on both lots, plus one unstressed control each.
- **Potency loss is driven by temperature and time, not humidity**, and the two
  formulations are statistically **indistinguishable** on potency.
- A **mass-balance gap**: at the harshest conditions ~35% of the active is lost
  while measured impurities stay near ~0.4% — so assay loss cannot be read as
  straightforward chemical degradation, and the mechanism is undetermined.
- Formulation **A is weakly preferred on impurities only** (lower RRT 1.23,
  p < 0.001); the difference is small.
- No Arrhenius / shelf-life extrapolation is attempted — the design and the
  mass-balance gap do not support it.

## Repository contents

```
stability_analysis.ipynb   # the analysis (run top-to-bottom)
requirements.txt
README.md
.gitignore                 # excludes the data file
data/                      # it needs to be created by the user
```

> The dataset is **not** committed to this repository (per the exercise
> instructions). To run the notebook, place `KTP_task_datasets.xls` in a
> `data/` folder at the repo root.

## Setup

Requires Python 3.10+.

```bash
git clone <https://github.com/adarshvaloor/KTP-Task-Sussex.git>
cd <repo>
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt

mkdir -p data
# copy KTP_task_datasets.xls into ./data/

jupyter lab        # or: jupyter notebook
```

Open `stability_analysis.ipynb` and run all cells (Kernel → Restart & Run All).
The legacy `.xls` is read with the `xlrd` engine.


