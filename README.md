# GA Feature Selection - Team Project -F24 - SVU

**Goal**: Use a Genetic Algorithm (GA) to select an optimal subset of features that maximizes model performance while minimizing the number of features. Build a web app to upload CSVs, run GA + baselines (PCA/Lasso), and show results. Host on Render/Heroku. Document all steps with Git.

## Repo Structure
```
.
├── app.py                     # Flask web app (upload CSV, show results)
├── src/
│   ├── pipeline.py            # Single entry-point used by the web app
│   └── ga_feature_select/
│       ├── __init__.py
│       ├── data_preprocessing.py
│       ├── ga_core.py         # GA loop (init, selection)
│       ├── operators.py       # crossover, mutation
│       ├── fitness.py         # fitness function definition(s)
│       └── baselines.py       # PCA/Lasso comparison
├── templates/
│   ├── index.html
│   └── results.html
├── static/
│   └── style.css
├── data/.gitkeep
├── docs/
│   └── report_outline.md
├── tests/
│   └── test_sanity.py
├── requirements.txt
├── runtime.txt
├── .gitignore
```

## Branching Model
- Protected: `main`
- Integration: `develop`
- Feature branches per person & task, e.g.:
  - `Bilal Alasha/feat-preprocessing`
  - `your name/feat-ga-core`
  - `your name/feat-operators`
  - `your name/feat-web-ui`
  - `oyour name/feat-baselines`
  - `your name /feat-experiments`
- PR required to merge into `develop`, then periodically merge `develop` → `main` after CI passes.

## Local Setup (Python 3.11 recommended)
```bash
python -m venv .venv
source .venv/bin/activate   # (Windows) .venv\Scripts\activate
pip install --upgrade pip
pip install -r requirements.txt
pre-commit install
```

## Run the web app locally
```bash
FLASK_APP=app.py FLASK_ENV=development flask run
# or
python app.py
```

Then open http://127.0.0.1:5000

## Deploy
# Unkown FOR NOW
## Next Steps
- Implement each module under `src/ga_feature_select` according to tasks:
  1) data_preprocessing.py
  2) fitness.py + chromosome (boolean mask implied by selected indices)
  3) ga_core.py (init + selection)
  4) operators.py (crossover + mutation)
  5) experiments via `src/pipeline.py` (collect metrics & artifacts in /data or /docs)
  6) baselines.py (PCA/Lasso)
  7) app.py + templates for web
  8) docs/report + hosting

## License
MIT
