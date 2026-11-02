# Gallbladder Disease Classification Using Machine Learning and Deep Learning

## Overview

Reading gallbladder ultrasound images is challenging because visual differences between disease categories can be subtle and highly variable. This research investigates and compares traditional machine learning and deep learning approaches for classifying **nine gallbladder disease categories** using a public ultrasound image dataset from Mendeley Data.

The study evaluates handcrafted image features, deep feature representations, classical machine learning algorithms, and transfer-learning-based convolutional neural networks to identify the most effective classification approach.

## Research Objectives

- Classify ultrasound images into nine gallbladder disease categories.
- Compare handcrafted feature engineering with deep learning representations.
- Evaluate six classical machine learning algorithms.
- Compare four transfer-learning architectures.
- Assess model performance using accuracy, precision, recall, and F1-score.
- Identify the best-performing model for gallbladder ultrasound image classification.

## Methodology

### 1. Dataset

The study uses a public gallbladder ultrasound image dataset obtained from Mendeley Data.

- **Classification task:** Nine disease categories
- **Test set size:** 1,604 images
- **Data splitting:** Stratified training, validation, and testing sets
- **Evaluation:** All models use the same data splits for a consistent comparison.
- **Dataset Link:**
https://data.mendeley.com/datasets/r6h24d2d3y/2.

### 2. Feature Extraction

Four image feature representations are investigated:

| Feature | Description |
|---|---|
| HOG | Histogram of Oriented Gradients captures image shape and edge information. |
| LBP | Local Binary Patterns describes local texture patterns. |
| GLCM | Gray-Level Co-occurrence Matrix extracts statistical texture properties. |
| ResNet50 embeddings | Deep feature representations learned by a pretrained convolutional neural network. |

The extracted features are concatenated into a single feature vector for classical machine learning.

### 3. Classical Machine Learning Models

The combined feature representation is evaluated using six algorithms:

1. Logistic Regression
2. K-Nearest Neighbors (KNN)
3. Support Vector Machine (SVM)
4. Random Forest
5. XGBoost
6. LightGBM

### 4. Deep Learning Models

Four convolutional neural network architectures are fine-tuned using transfer learning:

- MobileNetV3
- ResNet50
- DenseNet121
- EfficientNetB3

The models are trained and evaluated using consistent stratified data splits to enable a direct performance comparison.

## Results

The fine-tuned ResNet50 model achieved the best performance among the evaluated approaches.

| Model | Test Accuracy |
|---|---:|
| Fine-tuned ResNet50 | **99.56%** |
| LightGBM | 98.32% |

### Best Model: ResNet50

Performance on the 1,604-image test set:

| Metric | Score |
|---|---:|
| Accuracy | 99.56% |
| Macro Precision | 0.9944 |
| Macro Recall | 0.9956 |
| Macro F1-score | 0.9959 |

Macro-averaged metrics calculate the unweighted mean of the corresponding metric across all nine disease classes.

These results indicate that the fine-tuned ResNet50 model outperformed the strongest classical machine learning model, LightGBM, on the reported test accuracy.

## Evaluation Metrics

- **Accuracy:** Proportion of correctly classified images.
- **Precision:** Proportion of predicted class assignments that are correct.
- **Recall:** Proportion of actual class instances correctly identified.
- **F1-score:** Harmonic mean of precision and recall.

Macro-averaging gives equal weight to each disease category.

## Repository Structure

```text
gallbladderresearchpaper/
├── Gallbladder_Disease_Pipeline_v4.ipynb
├── gallbladderresult.docx
└── README.md
```

- `Gallbladder_Disease_Pipeline_v4.ipynb` — Research notebook containing the analysis and model pipeline.
- `gallbladderresult.docx` — Research results and documentation.
- `README.md` — Project overview, methodology, and reported findings.

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/rishita2201/gallbladderresearchpaper.git
   ```

2. Navigate to the project directory:

   ```bash
   cd gallbladderresearchpaper
   ```

3. Install Jupyter Notebook if required:

   ```bash
   pip install notebook
   ```

4. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `Gallbladder_Disease_Pipeline_v4.ipynb` and execute the notebook cells in sequence.

**Requirements:** Python and the libraries used by the notebook. Install the exact dependencies required by the implementation before running the complete pipeline. Dataset access, model downloads, and available hardware may affect execution.

## Key Findings

- Deep learning with fine-tuned ResNet50 achieved the highest reported test accuracy.
- LightGBM was the strongest classical machine learning model, reaching 98.32% accuracy.
- Combining handcrafted texture, gradient, and deep features provides a framework for evaluating classical classifiers.
- Using identical stratified splits supports a fairer comparison between the evaluated approaches.

## Limitations and Future Work

- Evaluate generalization on independent datasets from different clinical settings.
- Investigate class-wise errors, confusion matrices, and performance across individual disease categories.
- Assess robustness to image quality variations and differences in ultrasound acquisition.
- Validate the reported performance through external testing and prospective clinical studies.
- Explore model explainability to help researchers understand the visual evidence behind predictions.

## Clinical Disclaimer

This project is intended for academic research and educational purposes. The models are not validated for independent clinical diagnosis and should not replace professional medical judgment or radiologist interpretation.

## Acknowledgements

The study uses a publicly available gallbladder ultrasound dataset from Mendeley Data. Please refer to the original dataset record for its authorship, citation, licensing, and usage conditions.

---

*This repository presents a comparative research study of classical machine learning and transfer-learning approaches for gallbladder ultrasound image classification.*
