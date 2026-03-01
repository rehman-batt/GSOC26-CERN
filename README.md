# PyTorch DataLoader Benchmark

This repo contains a notebook that generates a synthetic dataset and benchmarks PyTorch DataLoader throughput and scaling efficiency.

## Reproducibility

These steps assume a clean system with Python 3.10+ and internet access for pip.
Download and install Python from https://www.python.org/downloads/.

### 1) Create and activate a virtual environment

**Linux/macOS:**
```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

**Windows (Command Prompt):**
```cmd
python -m venv .venv
.venv\Scripts\activate
python -m pip install --upgrade pip
```

### 2) Install dependencies

```bash
pip install -r requirements.txt
```

Notes:
- The benchmark uses CPU DataLoader workers, so GPU is not required.

### 3) Run the notebook

```bash
jupyter notebook PyTorchDataLoaderMicrobenchmark.ipynb
```

Open the notebook and run all cells from top to bottom.

### 4) Expected outputs

The notebook produces:
- A synthetic dataset under the `data/` directory (about 8 GB by default).
- Console logs for per-worker timing and throughput.
- Plots for throughput, time, and scaling efficiency.

## Tips for repeatable runs

- Keep the same `SEED`, `NUM_WORKERS`, `NUM_TRIALS`, and `BATCH_SIZE` values in the notebook.
- Close other heavy processes to reduce system noise during benchmarking.
- If you already have `data/` generated, you can skip the data generation cell and proceed to benchmarking.

## Troubleshooting

- If you see out-of-disk errors, reduce `TOTAL_SIZE_GB` in the notebook.
- If you see permission errors creating `data/`, ensure you have write access to the repo directory.

## AI Disclaimer

AI was used to help write markdown content in the notebook and some parts of the `SyntheticDataset` class. Help was also taken in writing the report. This README was also written with help from AI. 😅
