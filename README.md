# Land Use and Land Cover (LULC) Classification

A pipeline for classifying Land Use and Land Cover using Landsat SR imagery and ESRI LULC data. 

---


## Setup Instructions

### 1. Cloning the Repo
Clone the repository and navigate into the project directory:
```bash
git clone https://github.com/kartikgoyal137/LULC-Segmentation
cd LULC-Segmentation
```

### 2. Environment Creation
Create and activate a virtual environment to ensure dependency isolation.

####  Using `venv` (pip)

**Linux/macOS**
```bash
python -m venv venv
source venv/bin/activate
```

**Windows**
```bash
python -m venv venv
venv\Scripts\activate
```

#### Using `conda`
```bash
conda create -n lulc python=3.11.15
conda activate lulc
```

### 3. Python Version Verification
This project requires **Python 3.11.15** for full compatibility with the libraries used. Before proceeding, verify your version:
```bash
python --version
```
If the output is not exactly `Python 3.11.15`, please install the correct version from [python.org](https://www.python.org) before continuing.

### 4. Install Dependencies
Once the correct environment is active, install the required packages. This project relies on several key libraries including `torch`, `rasterio`, `rioxarray`, and `tqdm`.

**Using pip:**
```bash
pip install -r requirements.txt
```

**Using conda:**
```bash
conda install --file requirements.txt
```
---

## Project Structure
```
├── notebooks/
│   ├── Preprocessing.ipynb
│   ├── Data_Preparation.ipynb
│   └── Model.ipynb
├── utils/
│   └── helper.py
├── visualizations/
├── requirements.txt
└── README.md
```
- `notebooks/` - Contains the core logic for data processing and model training.
- `utils/helper.py` - A centralized script containing shared utility functions and class definitions used across the notebooks.
- `visualizations/` - Stores generated output patches and classification results for visual inspection.

---

## Execution Order
Execute the notebooks in the following sequence:

| Step | Notebook | Description |
|------|----------|-------------|
| 1 | `Preprocessing.ipynb` | Handles initial data downloading, cleaning, and coordinate transformations using `rasterio` and `rioxarray`. |
| 2 | `Data_Preparation.ipynb` | Performs patch generation from large satellite tiles and applies data augmentation techniques to enhance training diversity. |
| 3 | `Model.ipynb` | Defines the neural network architecture, manages the training loop, and evaluates performance metrics like Accuracy, IoU, Dice, etc.|
