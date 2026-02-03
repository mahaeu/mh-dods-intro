# DODS Notebooks (Starter + Analyzer Intro)

Two minimal Jupyter notebooks that demonstrate the typical DODS workflow:
1) generate example data with **dods.datagen**
2) inspect / analyze it with **dods.analyze**

---

## What’s included

- **Notebook 1 — “DODS Starter Notebook (DataGen + Analyze)”**
  - Lists templates
  - Creates a template (`template_long`)
  - Generates CSV datasets via `dg.run(...)`

- **Notebook 2 — “Data Analyzer Intro”**
  - Loads a generated CSV into pandas
  - Runs `DataAnalyzer` methods for quick insights and plots

This is intentionally compact and runnable. Put deeper docs into your main README later.

---

## Requirements

- Python 3.9+ (recommended 3.11.3)
- Jupyter (Notebook or Lab)
- `pandas`
- Your DODS packages:
  - `dods` (for `dods.datagen`)
  - `dods-analyze` (for `dods.analyze`) — if it’s split out

---

## Install

### Create a Virtual Environment
You can use pyenv, anaconda etc.

```python -m venv .venv```

Activate the virtual environment depending on your OS and start installing.
### Option A — install All at once
```bash
pip install dods 
pip install jupyterlab
```

### Option B - Install seperately
```bash
pip install dods-datagen
pip install dods-analyzer
pip install jupyterlab
```

---

## Minimal “sanity check” sequence

Run these in order:

```python
import dods.datagen as dg
dg.list_templates()
dg.create_template("template_long", overwrite=True)
dg.run("template")
```

Then:

```python
import pandas as pd
from dods.analyze import DataAnalyzer

df = pd.read_csv("data/template.csv")
DataAnalyzer(df).summary()
```
