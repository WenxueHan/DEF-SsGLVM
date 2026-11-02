# DEF-SsGLVM
Code, data, and per-run results for "A Semi-supervised Heterogeneous Generative Latent Variable Modeling Framework for Industrial Virtual Metrology".
Code, data, and experimental results accompanying the manuscript:

**A Semi-supervised Heterogeneous Generative Latent Variable Modeling Framework for Industrial Virtual Metrology**

DEF-SsGLVM is a dual-encoder flow-based implementation of the Hetero-SsGLVM framework for semi-supervised industrial quality prediction.

## Repository contents

- `code/`: model implementation, training scripts, and evaluation code.
- `data/`: datasets and sample indices defining the training, validation, and test splits.
- `configs/`: model configurations, training settings, and random seeds.
- `results/`: per-run predictions, test targets, and evaluation metrics.
- `requirements.txt`: Python dependencies and versions.

The experiments cover a synthetic dataset and two industrial datasets: the debutanizer column process (DCP) and the vacuum gas oil hydrotreating process (VGOHP).

## Experimental protocol

The synthetic dataset contains 2,000 samples, divided into 1,000 training samples, 500 validation samples, and 500 test samples.

The reported label rate applies only to the training set. Labeled training samples are selected according to this rate, and the remaining training samples are used as unlabeled data. At each label rate, all compared models use the same labeled and unlabeled training samples.

The validation and test sets are fully labeled and are used for hyperparameter selection and final evaluation, respectively. All models and label rates share the same fixed test set within each case study.

Hyperparameters are selected using validation RMSE, with grid search for the synthetic case and differential evolution for the industrial cases.

Dataset-specific split indices, preprocessing settings, and selected model configurations are provided in `data/` and `configs/`.

Tested environment:

- Python: 3.10
- PyTorch: 2.1.1
- Operating system: Windows 11, 64-bit
- Hardware: CPU: Intel Core i5-12400F, 2.50 GHz; Random Access Memory: 32 GB; Graphics Card: NVIDIA GeForce RTX 4060 (8 GB).

- ## Data availability

The synthetic dataset is included in this repository. However, the industrial datasets, cannot be publicly released due to confidentiality requirements imposed by the data-owning companies.

Accordingly, the raw and processed industrial data, dataset-specific sample indices, and any other files containing proprietary information are not included in this repository. The source code, model configurations, training settings, and experimental protocols are provided to facilitate the reproducibility of the proposed method. Access to the industrial datasets may be possible subject to the approval of the corresponding data owners.
