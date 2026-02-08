## Project Overview

This project implements **Principal Component Analysis (PCA)** using NumPy to analyze African CO2 emissions data. The implementation includes standardization, eigendecomposition, and dimension reduction.
- [Open the Notebook in Google Colab](https://colab.research.google.com/github/hd77alu/pca-ml/blob/main/PCA_Formative_2.ipynb)

## Project Structure
```
pca-ml/
├── README.md                                    
├── africa-co2-emissions.csv                     
├── PCA_Formative_2[Peer_Pair_Number].ipynb     
                                 
```

## Dataset Information

**Dataset:** `africa-co2-emissions.csv`

### Dataset Characteristics:
- **Rows:** 1,134
- **Columns:** 20 total (3 non-numeric, 17 numeric)
- **Missing Values:** 1,013 (handled via mean imputation)
- **Source:** [African countries CO2 emissions data](https://www.kaggle.com/datasets/victoraiyewumi/co2-emission-africa)

## Installation & Setup

### Step 1: Clone or Download the Repository
```bash
git clone https://github.com/hd77alu/pca-ml.git
cd pca-ml
```

### Step 2: Install Required Libraries
```bash
# Install Jupyter Notebook (if not already installed)
pip install jupyter

# Install required Python libraries
pip install numpy pandas matplotlib
```

## How to Use the Notebook

### Method 1: Using Google Colab
1. Click the "Open in Colab" badge at the top of the notebook
2. Upload `africa-co2-emissions.csv` to your files
3. Run all cells

### Method 2: Using VS Code
1. Open VS Code
2. Install the Jupyter extension (if not already installed)
3. Open the folder `pca-ml`
4. Click on `PCA_Formative_2.ipynb`
5. Select Run all 
6. Select Python kernel when prompted

### Method 3: Using Jupyter Notebook (Local)
```bash
# Navigate to project directory
cd pca-ml

# Launch Jupyter Notebook
jupyter notebook

# Open the file: PCA_Formative_2.ipynb
```


## PCA Implementation Steps

The notebook implements PCA in 7 steps:

### **Step 1: Load and Standardize Data**
- Loads the African CO2 emissions dataset
- Handles missing values via mean imputation
- Manual standardization using Z-score formula: `Z = (X - μ) / σ`
- **No sklearn used** - Pure NumPy implementation

### **Step 2: Calculate Covariance Matrix**
- Computes 17×17 covariance matrix
- Shows feature correlations

### **Step 3: Eigendecomposition**
- Calculates eigenvalues and eigenvectors
- Uses `np.linalg.eig()` for decomposition

### **Step 4: Sort Principal Components**
- Sorts eigenvalues in descending order
- Calculates explained variance ratios
- **Analysis:** 5 components capture 88.41% of variance
  - PC1: 51.22%
  - PC2: 13.53%
  - PC3: 9.50%
  - PC4: 8.21%
  - PC5: 5.95%

### **Step 5: Project Data onto Principal Components**
- Matrix multiplication: `reduced_data = standardized_data × eigenvectors`
- Transforms 17 dimensions → 5 dimensions

### **Step 6: Output Reduced Data**
- Displays transformed data as DataFrame
- Shows dimensionality reduction: 70%.6 reduction (from 17 to 5 features)

### **Step 7: Visualize Before and After PCA**
- **Left Plot:** Original data (2 CO2 emission features)
- **Right Plot:** PCA-transformed data (PC1 vs PC2)
- Demonstrates variance captured by principal components

### Key Insights:
- First principal component captures >50% of total variance
- Top 2 components capture ~65% of variance
- 5 components sufficient to retain 88%+ of information
- Successfully reduces complexity while preserving data structure