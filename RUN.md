# How to Run the Notebooks

Follow these steps to reproduce the Lab 2.4 ETL notebook and its artifacts.

## 1) Clone and set up the environment
1. Clone the repository and enter the folder:
   ```bash
   git clone <repo-url>
   cd csai-382-repos-and-notebooks
   ```
2. (Optional) Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```
3. Install dependencies (pandas, PyYAML, numpy) or run with the built-in pure-Python fallback:
   ```bash
   pip install -r requirements.txt
   ```
   If you cannot install packages, the notebook will still run using the standard library.

## 2) Data availability
- The Week 1 datasets are stored in the `data/` directory:
  - `data/menu_items.csv`
  - `data/order_details.csv`
- These files are read directly by the notebooks; no additional downloads are required.

## 3) Run `notebooks/lab_2_4_repro_logging.ipynb`
1. Launch Jupyter Lab or Jupyter Notebook:
   ```bash
   jupyter lab
   ```
   or
   ```bash
   jupyter notebook
   ```
2. Open `lab_2_4_repro_logging.ipynb` and run all cells in order. The notebook sets seeds, configures logging, hashes the input CSVs, and computes three metrics.
3. Artifacts produced during the run:
   - Timestamped log file in `logs/run_*.log`.
   - Data hashes in `data_hashes.json`.
   - Stacked metrics CSV in `etl_pipeline/metrics_*.csv`.
   - Updated `requirements.txt` from the current environment.

## 4) Optional configuration
- Edit `config.yaml` to change data, log, or output directories. If PyYAML is installed, the notebook will read these overrides; otherwise, it will use the defaults baked into the code.
