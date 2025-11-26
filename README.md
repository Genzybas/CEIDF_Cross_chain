# CEIDF: Cross-Chain Energy-Aware IDS Framework
```markdown


CEIDF is a cross-chain intrusion detection framework for IoT environments that combines deep learning–based detection, model compression (pruning, quantization, distillation), and blockchain interoperability to achieve high accuracy with reduced energy consumption on resource-constrained devices.

## Features

- Cross-chain deployment of IDS models across heterogeneous blockchain networks via an interoperability layer (LayerZeroIBC-style).
- Energy-aware model compression using pruning, quantization, and knowledge distillation.
- Support for public intrusion detection datasets (e.g., CICIDS2017, BoT-IoT).
- End-to-end pipelines for data preprocessing, training, evaluation, and energy measurement.
- Reproducible experiments with documented hyperparameters, seeds, and statistical reporting.

## Repository Structure

- `configs/` – Configuration files for datasets, models, and hyperparameters.
- `data/` – Scripts or instructions to download and preprocess datasets.
- `models/` – Model definitions, training scripts, and checkpoints.
- `contracts/` – Smart contract code and cross-chain messaging interfaces.
- `energy/` – Scripts for device-level energy measurement and log processing.
- `experiments/` – Scripts/notebooks to reproduce paper figures and tables.
- `results/` – Aggregated metrics, plots, and statistical summaries.
- `scripts/` – Utility scripts for setup, running experiments, and evaluation.

Adjust folder names to match your actual repo.

## Installation

```
git clone [https://github.com/Genzybas/CEIDF_Cross_chain](https://github.com/Genzybas/CEIDF_Cross_chain.git)
cd REPO_NAME

python -m venv .venv
# Linux/macOS
source .venv/bin/activate
# Windows
# .venv\Scripts\activate

pip install -r requirements.txt
```

## Datasets

This project supports standard IDS datasets such as CICIDS2017 and BoT-IoT.

1. Download each dataset from its official source.
2. Place the raw files as described in `data/README.md`.
3. Run the preprocessing scripts to generate train/val/test splits.
4. Update dataset paths in the corresponding files under `configs/`.

Raw datasets are not included in this repository.

## Usage

### Train baseline models

```
python scripts/train_baseline.py --config configs/baseline_cicids2017.yml
```

### Run compression (pruning, quantization, distillation)

```
python scripts/run_compression.py --config configs/compression_cicids2017.yml
```

### Evaluate models

```
python scripts/eval_model.py --config configs/eval_cicids2017.yml
```

### Deploy cross-chain setup

```
python scripts/deploy_cross_chain.py --config configs/cross_chain.yml
```

### Measure energy on device

```
python energy/measure_energy.py --config configs/energy_rpi.yml
```

## Reproducibility

- All experiments are driven by config files in `configs/`.
- Hyperparameters (learning rate, batch size, pruning threshold, quantization precision, distillation temperature, etc.) are documented in the paper’s Table Y and mirrored in this repository.
- Each reported result is averaged over multiple seeds; aggregated statistics (mean, standard deviation, confidence intervals) are stored under `results/`.

See `experiments/README.md` for exact commands to reproduce the main figures and tables.

## Data and Code Availability

During double-blind review, an anonymized version of this repository (without author-identifying information) is shared with reviewers.

After acceptance, the camera-ready paper will include:

- The public GitHub URL of this repository.
- A permanent archival link (e.g., DOI) pointing to a frozen snapshot of the code and models.

## Citation

If you use this framework in your work, please cite the associated paper:

```
@article{AUTHOR2025CEIDF,
  title   = {Cross-Chain and Energy-Efficient Intrusion Detection for IoT Se-
curity using Smart Contracts and Machine Learning},
  author  = {Bassey Samuel},
  journal = {JOURNAL_OR_CONFERENCE},
  year    = {2025}
}
```

Replace the placeholder fields with the final bibliographic information.

## License

Specify your license here (e.g., MIT, Apache-2.0, GPL-3.0) and add a matching `LICENSE` file:

```
This project is licensed under the MIT License – see the LICENSE file for details.
```
```

