# 🧠 Brain Tumor Detection Using CNN and Transfer Learning

This project aims to classify brain MRI images as **healthy** or **tumorous** using two different approaches:

1. A custom-built **Convolutional Neural Network (CNN)**
2. **Transfer Learning** with MobileNet as the base model

---

## 📁 Dataset Structure

The dataset should be organized in the following folder structure:

```
Dataset/
🔹 healthy/
🔹 tumor/
```

#### Sample Image 

Images of the Brain Tumor and Healthy Brain.

- **Healthy:**
  <p float="left">
    <img src="Dataset\healthy\healthy (1).jpg" width="100%" />
    <img src="Dataset\healthy\healthy (50).jpg" width="100%" />
    <img src="Dataset\healthy\healthy (388).jpg" width="100%" />
    <img src="Dataset\healthy\healthy (408).jpg" width="100%" />
  </p>

- **Tumor:**
  <p float="left">
    <img src="Dataset\tumor\tumor (1).jpg" width="100%" />
    <img src="Dataset\tumor\tumor (50).jpg" width="100%" />
    <img src="Dataset\tumor\tumor (388).jpg" width="100%" />
    <img src="Dataset\tumor\tumor (408).jpg" width="100%" />
  </p>

Each image is an MRI scan labeled as either *healthy* or *tumor*.

Download Dataset: [Kaggle Dataset](https://www.kaggle.com/datasets/hamzahabib47/brain-cancer-detection-mri-images/data)
---

## 📦 Requirements

Install the required libraries using:

```bash
pip install tensorflow numpy matplotlib
```

---

## 🚀 Project Workflow

### 1. 📊 Data Preparation

* The dataset is split into:

  * `train/` (70%)
  * `val/` (15%)
  * `test/` (15%)
* A custom `dataFolder()` function performs the splitting.

### 2. 🧠 Model Architectures

#### ✅ CNN from Scratch

* Built using Keras `Sequential` model
* Contains:

  * 3 convolutional blocks
  * Dropout layers for regularization
  * Final dense layer with `sigmoid` for binary classification

#### 🔄 Transfer Learning

* MobileNet is used as the base model
* Fully connected layers are added on top
* Base layers are frozen initially to use pretrained features

### 3. 📈 Training & Callbacks

* **EarlyStopping** and **ModelCheckpoint** are used to avoid overfitting and save the best model.
* `binary_crossentropy` loss and `Adam` optimizer are used.

---

## 📊 Results

| Model             | Validation Accuracy | Test Accuracy |
| ----------------- | ------------------- | ------------- |
| CNN (Scratch)     | \~92.66%             | \~91.74%      |
| Transfer Learning | \~100%             | \~97.24%      |

> 📌 *The transfer learning model converged faster and generalized better.*


---

## 📉 Visualizations

* Training vs Validation Accuracy and Loss are plotted after training.
* Misclassifications can be analyzed visually using `matplotlib`.

---

## 💡 Future Improvements

* Use more advanced architectures (e.g., EfficientNet)
* Add Grad-CAM visualization for model interpretability
* Handle class imbalance (if any) using techniques like oversampling

---

## 📌 License

This project is for educational purposes.

---