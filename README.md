# Lung Nodule Stage Classification (DCT / LDCT / ILBP / BPD-LDCT)

Notebooks that extract image features and train an SVM to classify nodule stage.

## Folder Structure
root/
│
├── Stage 1/
│   ├── AUTid/
│   │   ├── DCT.ipynb
│   │   ├── LDCT.ipynb
│   │   ├── ILBP.ipynb
│   │   └── BPD-LDCT.ipynb
│   └── TDId/
│       ├── DCT.ipynb
│       ├── LDCT.ipynb
│       ├── ILBP.ipynb
│       └── BPD-LDCT.ipynb
│
└── Stage 2/
    ├── AUTid/
    │   ├── DCT.ipynb
    │   ├── LDCT.ipynb
    │   ├── ILBP.ipynb
    │   └── BPD-LDCT.ipynb
    └── TDId/
        ├── DCT.ipynb
        ├── LDCT.ipynb
        ├── ILBP.ipynb
        └── BPD-LDCT.ipynb
```
- **Stage 1 / Stage 2** = which label column is used as the target (`Stage_1` = coarse label, `Stage_2` = fine-grained label).
- **AUTid / TDId** = two different datasets (same pipeline, different data source).
- **DCT / LDCT / ILBP / BPD-LDCT** = four different feature extraction methods; rest of the pipeline is the same.

## Requirements
```
python 3.10
numpy==1.23.5
matplotlib==3.6.3
scikit-learn==1.1.3
imbalanced-learn==0.10.1
pandas
opencv-python
scipy
```
Install:
```bash
pip install numpy==1.23.5 matplotlib==3.6.3 scikit-learn==1.1.3 imbalanced-learn==0.10.1 pandas opencv-python scipy
```

## Data
- **Labels CSV** (`Labels.csv`): columns `Image, Stage_1, Stage_2`.
- **Images folder**: `All_images/All_images/`, one flat folder of image files.
- Labels are matched by filename: each image's name (without extension) is looked up in the `Image` column to get its `Stage_1`/`Stage_2` label.


## How to Run
1. Install requirements above.
2. Update the paths at the top of the notebook (they currently point to Kaggle paths like `/kaggle/input/...` and `/kaggle/working`) to your local data/output folders.
3. Run all cells top to bottom in Jupyter.
4. Outputs: trained SVM models (`.pkl`) and a `fold_predictions.csv` with results.
