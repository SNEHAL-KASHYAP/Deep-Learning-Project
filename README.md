# NeuroShield-IDS 🛡️
### Deep Learning-Based Intrusion Detection System Using NSL-KDD

## 📌 Overview

NeuroShield-IDS is a deep learning-based Intrusion Detection System (IDS) that classifies network traffic records as normal or malicious. It uses the **NSL-KDD dataset** to train and evaluate deep neural networks for binary and multiclass intrusion detection.

The project explores how deep learning can help identify suspicious network activity and categorize different types of cyberattacks.

## 🎯 Objectives

- Develop a Deep Neural Network (DNN) for intrusion detection.
- Classify network traffic into **Normal** and **Attack** classes.
- Categorize traffic into five classes: Normal, DoS, Probe, R2L, and U2R.
- Apply preprocessing techniques to numerical and categorical features.
- Explore class-weighted training to address imbalanced attack categories.
- Evaluate model performance using classification metrics and confusion matrices.
- Test the trained models on custom NSL-KDD-format connection records.

## 📊 Dataset

This project uses the **NSL-KDD dataset**, a benchmark dataset for network intrusion detection research.

The main files used are:

- `KDDTrain+.txt` — training dataset
- `KDDTest+.txt` — testing dataset

Download the dataset from the [UNB Canadian Institute for Cybersecurity NSL-KDD page](https://www.unb.ca/cic/datasets/nsl.html).

**Note:** Download and upload the dataset to your Google Colab environment or mount it from Google Drive before running the notebook. The dataset files are not included in this repository.

## 🧠 Classification Tasks

### 1. Binary Classification

The binary model predicts whether a network traffic record is:

- **Normal (0):** Legitimate network activity
- **Attack (1):** Network activity associated with an attack

### 2. Multiclass Classification

The multiclass model categorizes traffic into five broad classes:

| Class | Description |
|---|---|
| Normal | Legitimate network activity |
| DoS | Denial of Service attacks |
| Probe | Scanning and information-gathering attacks |
| R2L | Remote-to-Local attacks |
| U2R | User-to-Root attacks |

## ⚙️ Model Architecture

The project uses a Deep Neural Network with five fully connected hidden layers.

- Hidden layers: 1024, 768, 512, 256, and 128 neurons
- Activation: ReLU
- Batch Normalization
- Dropout: 0.01
- Optimizer: Adam
- Learning rate: 0.001
- Binary output: Sigmoid
- Multiclass output: Softmax

The binary model uses binary cross-entropy loss, while the multiclass model uses sparse categorical cross-entropy loss.

A class-weighted multiclass model is also trained to help address the imbalance between common and rare attack categories.

## 🔄 Workflow

1. Load the NSL-KDD training and testing datasets.
2. Separate input features and target labels.
3. Encode categorical features using one-hot encoding.
4. Scale and normalize the input features.
5. Prepare binary and multiclass labels.
6. Build and train the deep learning models.
7. Evaluate predictions on the test dataset.
8. Generate classification reports and confusion matrices.
9. Test custom connection records using the trained models.

## 🛠️ Technologies Used

- Python
- Google Colab
- TensorFlow / Keras
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn

## 🚀 How to Run

### Step 1: Open the notebook

Open the `.ipynb` notebook included in this repository using Google Colab.

### Step 2: Download the dataset

Download the NSL-KDD dataset and upload `KDDTrain+.txt` and `KDDTest+.txt` to your Colab environment, or place them in the appropriate folder in Google Drive.

### Step 3: Install dependencies

Run this in a notebook cell if the required libraries are not already available:

```python
%pip install tensorflow pandas numpy scikit-learn matplotlib seaborn
```

### Step 4: Configure dataset paths

Update the dataset paths in the notebook to match where the files are stored.

### Step 5: Run the notebook

Execute the notebook cells in order to preprocess the data, train the models, and evaluate their performance.

**Important:** Training cells must be run before prediction cells. If the Colab runtime restarts, rerun the required preprocessing and setup cells or reload saved models and preprocessing objects.

## 📈 Evaluation

Model performance can be assessed using:

- Accuracy
- Precision
- Recall
- F1-score
- AUC (for binary classification)
- Confusion matrix

The project also examines the performance of individual attack categories. Since the NSL-KDD dataset is imbalanced, results for rare classes such as R2L and U2R may be weaker than results for common classes.

Actual results should be taken from the notebook execution and reported without alteration.

## 🔬 Research Reference

This project is inspired by the following research paper:

Vinayakumar, R., Alazab, M., Soman, K. P., Poornachandran, P., and Venkatraman, S. (2019). *Deep Learning Approach for Intelligent Intrusion Detection System*. IEEE Access, 7, 41525–41550.

DOI: [10.1109/ACCESS.2019.2895334](https://doi.org/10.1109/ACCESS.2019.2895334)

This is a research-inspired implementation and should not be considered an exact reproduction of the paper's complete experimental setup.

## ⚠️ Limitations

- The models are trained and evaluated on NSL-KDD records.
- Custom predictions require feature values in the expected NSL-KDD format.
- The project does not independently capture live network packets.
- Performance on benchmark data does not guarantee equivalent performance on real-world network traffic.
- Rare attack classes may be difficult to identify reliably.

## 🔮 Future Scope

- Integrate live network traffic capture and feature extraction.
- Evaluate the models on additional intrusion detection datasets.
- Improve detection of rare attack categories.
- Develop a web-based dashboard for interactive predictions.
- Explore real-time alerting and deployment.

## 👨‍💻 Project Information

**Project Name:** NeuroShield-IDS  
**Domain:** Deep Learning and Cybersecurity  
**Dataset:** NSL-KDD  
**Implementation Environment:** Python and Google Colab

## 📜 Disclaimer

This project is intended for educational and research purposes. It is not a replacement for a production-grade network security monitoring system.
