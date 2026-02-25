# Machine Learning Challenge

## Overview
This repository contains the solutions for two related machine learning tasks focused on data classification and noise reduction. Both tasks utilize the MNIST dataset of handwritten digits to demonstrate different machine learning capabilities.

## Dataset
The project uses the `mnist_784` dataset, imported via `sklearn.datasets.fetch_openml`. Each instance represents a 28x28 pixel image (flattened to 784 features) of a handwritten digit from 0 to 9.

---

## Task 1: Multi-Label Classification

### Objective
To build a machine learning model capable of predicting two distinct labels for a single image simultaneously.

### Methodology
* **Data Preparation:** The original target labels were transformed into a multi-label format consisting of two boolean columns:
  1. **Odd or Not:** Indicates whether the digit is odd (True) or even (False).
  2. **Greater Than 5:** Indicates whether the digit is strictly greater than 5 (True) or not (False).
* **Model Selection:** Implemented a `KNeighborsClassifier`, which is well-suited for handling multi-label classification tasks.
* **Evaluation:** The model's performance is assessed using:
  * **Accuracy Score:** To measure the exact match of both labels.
  * **Macro F1-Score:** To evaluate the harmonic mean of precision and recall across all labels.

---

## Task 2: Noise Removal Using Machine Learning

### Objective
To develop a regression-based machine learning pipeline that can effectively reconstruct clean images from inputs corrupted by random noise.

### Methodology
* **Data Preprocessing:** All image pixel values were normalized to a scale of 0.0 to 1.0.
* **Noise Injection:** Random Gaussian noise was artificially added to the images to simulate corrupted data. The resulting values were clipped to remain within the valid 0.0 to 1.0 range.
* **Dimensionality Reduction:** Applied Principal Component Analysis (PCA) to compress the input features (from 784 to 60 components). This crucial step optimizes computational efficiency without heavily compromising data integrity.
* **Model Selection:** Trained a `KNeighborsRegressor` model to predict the original, clean pixel values based on the noisy input data.
* **Evaluation & Visualization:** * **Metrics:** Evaluated mathematically using Mean Squared Error (MSE) and Mean Absolute Error (MAE).
  * **Visual Inspection:** Utilized Matplotlib to plot and compare the original target image, the noisy input image, and the final denoised prediction side-by-side.

---

## Dependencies
To execute the notebooks successfully, the following Python libraries are required:
* `numpy`
* `scikit-learn`
* `matplotlib`

## Instructions
Open the respective Jupyter Notebooks (`Task 1.ipynb` and `Task 2.ipynb`) and execute the cells sequentially. Please note that downloading the dataset during the first execution may take a few moments.