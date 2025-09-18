# Radiomic Analysis Applied to Prostate MRI

This repository contains all the research work carried out as part of my research project, focusing on radiomic analysis applied to prostate MRI.

##  Table of Contents

- [Project Content](#project-content)
- [Dataset](#dataset)
- [Folder Structure](#folder-structure)
- [Installation and Prerequisites](#installation-and-prerequisites)
- [Usage](#usage)

##  Project Content

The project follows the main steps of a complete radiomic pipeline:

### 1. Radiomic Feature Extraction
** Notebook:** `ADC_T2_Features_Extractions.ipynb`

From diffusion MRI (ADC) and T2-weighted sequences, radiomic features are extracted for each segmented lesion (masks provided).

### 2. Classification Model Training
** Notebooks:**
- `T2_ProstateX_Model_Training.ipynb`
- `ADC_ProstateX_Model_Training.ipynb`

**Objective:** Train and evaluate classification models on the extracted features.

### 3. Statistical Analysis and Visualizations
** Notebook:** `statistic_analysis.ipynb`

Generation of graphs and descriptive statistics to explore feature distribution according to Gleason grades.

##  Dataset

The `lesions` dataset contains:

### Prostate MRI Images
- **T2**: T2-weighted images
- **ADC**: Diffusion images

### Annotations
- **Masks**: Segmentations of tumor regions
- **Organization by Gleason grade (GG1–GG5)**

> **Note:** Before extraction, images are normalized based on their masks in the `Img_msk_resampled` folder.

##  Folder Structure

```
lesions/
│
├── T2/                      # T2-weighted MRI images
├── ADC/                     # ADC MRI images
├── Patient_ID/              # Patient indexing by Gleason grade
│   ├── GG1/
│   ├── GG2/
│   ├── GG3/
│   ├── GG4/
│   └── GG5/
│
├── Img_msk_resampled/       # Images normalized by masks
│   ├── GG1/
│   ├── GG2/
│   ├── GG3/
│   ├── GG4/
│   └── GG5/
│
├── ADC_T2_Images_Analyses/  # Extracted radiomic features
│
└── Masks/                   # Masks for each image (T2 and ADC)
    ├── T2/
    └── ADC/
```

## ⚙️ Installation and Prerequisites

### Installation Steps

1. **Create a virtual environment**
   ```bash
   python -m venv radiomics_env
   source radiomics_env/bin/activate  # Linux/Mac
   # or
   radiomics_env\Scripts\activate     # Windows
   ```

2. **Install Jupyter Notebook**
   ```bash
   pip install jupyter
   ```

3. **Download the data**
   - Download data from the associated Google Drive link
   - Unzip the `lesions.zip` file in the cloned folder

4. **File organization**
   - Place the `ADC_T2_Features_Extractions.ipynb` notebook in the same directory as the `lesions` folder

5. **Install libraries**
   ```bash
   pip install -r requirements.txt
   ```

### Main Dependencies

- `pyradiomics`
- `SimpleITK`
- `numpy`
- `pandas`
- `scikit-learn`
- `matplotlib`
- `seaborn`
- `jupyter`

##  Usage

1. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

2. **Execute notebooks in the following order:**
   1. `ADC_T2_Features_Extractions.ipynb` - Feature extraction
   2. `T2_ProstateX_Model_Training.ipynb` or `ADC_ProstateX_Model_Training.ipynb` - Model training
   3. `statistic_analysis.ipynb` - Statistical analysis and visualizations

##  Results

Analysis results are stored in the `ADC_T2_Images_Analyses/` folder and include:
- Extracted radiomic features
- Model performance metrics
- Statistical visualizations


*This project is part of research on radiomic analysis applied to prostate cancer diagnosis using MRI.*