# Approach A Code and Model Files

**Date:** 18/10/2024  
**Author:** Max Brenner  

This folder contains the code and models for **Approach A** as described in the paper "*Automatic Diagnosis of Cardiac Arrhythmias from 12-lead ECG Data Using Machine Learning Algorithms*."

**Note:** Due to storage constraints, the data used to train and test the models is excluded from this repository but can be downloaded from [Zenodo](https://zenodo.org/records/4916206) [1].

---

## Contents

### A) Approach_A_Data_Preprocessing_1.ipynb
This notebook is used to obtain a smaller, cleaned dataset from each part of the downloaded dataset. It removes cases where all arrhythmias are false, and normal ECG is also false, creating a reduced `.hdf5` file with the remaining ECGs and a corresponding `.csv` file with arrhythmia labels and patient details.

### B) Approach_A_Data_Preprocessing_2.py
This script merges the arrhythmia labels from the `.csv` file with the corresponding ECG tracings from the `.hdf5` file to create a new combined `.h5` file.

### C) Approach_A_Data_Preprocessing_3.py
This optional script combines all testing data into a single `.h5` file for convenience, especially useful for machines with limited RAM.

### D) Approach_A_Data_Loading_and_Model_Training.ipynb
This notebook provides the complete model training pipeline. It starts by loading and filtering the test data, then defines the model, learning rate, and training parameters. Finally, it initiates training, saving the normalization constants, the trained model, and periodic checkpoints throughout the training process.

### E) Approach_A_Testing_and_Validation.ipynb
This notebook includes the testing and validation protocols for the models trained using Approach A.

### F) Trained Model Files
The trained model is provided in both `.keras` and `.h5` formats:
- `trained_model.keras`
- `trained_model.h5`

Please use the format compatible with your Keras version.

### G) Normalization Data
Mean, standard deviation, and normalization data are included for consistency in testing:
- `train_mean.npy`
- `train_std.npy`
- `normalization_data.txt`

---

## Requirements

To run the code as intended, please ensure the following:

1. **Database**: Parts 0 to 17 of the database must be downloaded.
2. **File Paths**: Confirm that all file paths and names are correct.
3. **Sufficient RAM**: Ensure adequate RAM; if limited, consider batching the training process.
4. **Normalization Consistency**: Save your normalization constants (mean and standard deviation) from the training data and use them consistently for testing.

---

## References

[1] A. H. Ribeiro et al., “CODE-15%: a large scale annotated dataset of 12-lead ECGs.” *Zenodo*, Jun. 09, 2021. DOI: [10.5281/zenodo.4916206](https://doi.org/10.5281/zenodo.4916206).
