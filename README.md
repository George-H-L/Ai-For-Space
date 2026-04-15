# CNN Models for Remote Sensing: SAT-6 Classification

Group research project applying Convolutional Neural Network (CNN) architectures to the SAT-6 satellite imagery dataset for land cover classification.

## Team
- **Ehsan**: Data & Preprocessing (dataset, class mapping, preprocessing, dataloaders)
- **Oliver**: Model 1: ResNet18 (baseline training, validation, checkpoints)
- **Luca**: Model 2: ResNet50 (main model, tuning, scheduler)
- **George & Tausif**: Evaluation & Report (metrics, plots, comparison, results & discussion)

## Repository Structure
├── notebooks/
│   ├── preprocessing.ipynb       # Data loading, cleaning, splits
│   ├── resnet18_training.ipynb   # ResNet18 baseline
│   ├── resnet50_training.ipynb   # ResNet50 main model
│   └── evaluation.ipynb          # Metrics, comparison, visualisations
├── src/                          # Shared utility code
├── data/                         # Dataset location (not tracked in Git)
├── results/                      # Model outputs, plots, metrics
├── requirements.txt              # Pinned dependencies (TBC by Ehsan)
└── README.md

## Dataset
**SAT-6**: 6-class land cover classification dataset derived from the National Agriculture Imagery Program (NAIP). Contains ~405,000 image patches (28×28 pixels, 4 spectral bands).

Classes: building, barren land, trees, grassland, road, water.

Download from [Kaggle](https://www.kaggle.com/datasets/crawford/deepsat-sat6) and place in the `data/` folder, or use the shared Google Drive folder.

## Workflow

### Preprocessing (Google Colab)
Preprocessing is run in Google Colab to keep the data pipeline consistent across the team. Ehsan owns this stage. Open the preprocessing notebook directly in Colab:

- [Preprocessing notebook](https://colab.research.google.com/github/George-H-L/Ai-For-Space/blob/main/notebooks/preprocessing.ipynb)

Mount the shared Google Drive folder to access the raw dataset. Processed train/val/test splits are saved back to the shared Drive folder so the rest of the team can pull from a single source of truth.

** Google Drive Link **
https://drive.google.com/drive/folders/1zAzklidTDHZN1X5x6CIwO0e7dgrOUX58?usp=sharing

### Training & Evaluation (Colab or local Jupyter)
Once preprocessing is complete, training and evaluation can be run either in Colab or in local Jupyter, depending on each member's preference and hardware.

**Open in Colab:**
- [ResNet18 Training](https://colab.research.google.com/github/George-H-L/Ai-For-Space/blob/main/notebooks/resnet18_training.ipynb)
- [ResNet50 Training](https://colab.research.google.com/github/George-H-L/Ai-For-Space/blob/main/notebooks/resnet50_training.ipynb)
- [Evaluation](https://colab.research.google.com/github/George-H-L/Ai-For-Space/blob/main/notebooks/evaluation.ipynb)

**Run locally in Jupyter:**
1. Clone the repo: `git clone https://github.com/George-H-L/Ai-For-Space.git`
2. Install dependencies: `pip install -r requirements.txt`
3. Download the preprocessed splits from the shared Drive folder into `data/`
4. Open notebooks: `jupyter notebook`

Note: `requirements.txt` will be populated by Ehsan once preprocessing dependencies are finalised. To keep results comparable across machines, anyone running locally should match the package versions specified there.

## Methodology
1. **Preprocessing**: Data loading, normalisation, augmentation, train/val/test split *(details TBC by Ehsan)*
2. **Models**:
   - ResNet18: baseline architecture *(training details TBC by Oliver)*
   - ResNet50: main model with tuning and learning rate scheduling *(details TBC by Luca)*
3. **Evaluation**: Comparative analysis across models *(metrics TBC by George & Tausif)*

## Reproducibility
- Fixed random seed across all notebooks *(seed value TBC by Ehsan)*
- Pinned package versions in `requirements.txt` *(TBC by Ehsan)*
- Preprocessed data splits saved to shared Drive folder
