# MASER EEG Spatial Super-Resolution Reproduction

## Project Overview
This project presents a simplified MASER-inspired deep learning baseline for EEG spatial super-resolution. The objective is to reconstruct high-resolution EEG signals from low-resolution EEG channel inputs using PyTorch.

## Dataset
- **Dataset:** PhysioNet EEG Motor Movement/Imagery Dataset (EEGMMIDB)
- **Subjects:** First 10 subjects
- **Runs:** 4, 8, and 12
- **Sampling Frequency:** 160 Hz
- **Input Channels:** 16
- **Target Channels:** 64

The dataset is obtained through the MNE EEGBCI dataset interface. The dataset is not included in this repository.

## Preprocessing
- Band-pass filtering: 0.5–40 Hz
- Resampling to 160 Hz
- One-second overlapping windows
- Window stride: 0.5 seconds
- Train/validation/test split: 70:10:20
- Normalization using training target statistics

## Model Architecture
The simplified baseline includes:
- Channel expansion
- Convolutional input projection
- Three simplified EMamba blocks
- Channel attention and residual connections
- Convolutional output projection

**Note:** This is a simplified MASER-inspired implementation, not an exact reproduction of the original architecture.

## Experimental Configuration
- Framework: PyTorch
- Environment: Google Colab
- GPU: NVIDIA T4
- Epochs: 20
- Batch size: 16
- Learning rate: 0.001
- Optimizer: Adam

## Evaluation Results

| Metric | Reproduced Result |
|---|---:|
| nMSE | 0.149942 |
| PCC | 0.922366 |

## Repository Files
- `MASER_EEG_Reproduction.ipynb` – Complete implementation notebook
- `requirements.txt` – Required Python libraries
- `README.md` – Project documentation

## How to Run
1. Open the notebook using Google Colab.
2. Install the required libraries.
3. Run the notebook cells sequentially.
4. Allow the dataset to be downloaded through MNE.
5. Execute preprocessing, model training, and evaluation cells.
6. Review the evaluation metrics and generated figures.

## Dataset Source
PhysioNet EEG Motor Movement/Imagery Dataset:

https://physionet.org/content/eegmmidb/1.0.0/

## Research Paper
Add the complete original research paper title, DOI, and permanent URL here.

## Limitations
This experiment uses only the first 10 subjects and a simplified model architecture. Its results are therefore not directly equivalent to the original paper's experimental results.
