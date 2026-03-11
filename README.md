# ACNR (Automated Currency Note Recognition) 💵

An image classification project that uses Convolutional Neural Networks (CNN) to automatically recognize and classify different currency notes.

---

## 📋 Project Overview

This project implements a deep learning model to classify currency notes from images using TensorFlow/Keras. The model is trained on a custom dataset split into train, validation, and test sets (70/15/15), and can predict the denomination of currency notes with confidence scores.

---

## ✨ Features

- **Automated Dataset Splitting**: Randomly splits dataset into 70% train, 15% validation, 15% test
- **Image Classification**: Automatically identifies different currency note denominations
- **Visual Analysis**:
  - Sample image grid from the training set
  - Training/Validation accuracy and loss graphs
  - Confusion matrix heatmap
  - Classification report (precision, recall, F1-score)
  - Sample predictions with colour-coded correct/incorrect labels
  - Prediction distribution histogram on test data
  - Bar chart of test accuracy vs. loss
- **Interactive Prediction**: Upload custom images to get real-time predictions with top-3 confidence scores
- **Model Persistence**: Saves the trained model to Google Drive

---

## 📊 Dataset

The dataset contains images of different currency note denominations organized in folders by class.

**Download Dataset:**
[Download from Google Drive](https://drive.google.com/file/d/1GeD_AvjWY-n2F1PU-DkUakdeHr9dmsTW/view?usp=drive_link)

**Dataset Structure:**

```
Dataset/
├── Class_1/
│   ├── image1.jpg
│   ├── image2.jpg
│   └── ...
├── Class_2/
│   ├── image1.jpg
│   └── ...
└── ...
```

---

## 🚀 Getting Started

### Prerequisites

This project is designed to run on **Google Colab** with GPU acceleration.

Required libraries:

- TensorFlow/Keras
- NumPy
- Matplotlib
- Scikit-learn
- Seaborn

### Installation & Setup

1. **Open Google Colab**
   - Click the **Open in Colab** badge at the top of the notebook, or go to [Google Colab](https://colab.research.google.com/) and upload the notebook file

2. **Upload Dataset to Google Drive**
   - Download the dataset from the link above
   - Upload `Dataset.zip` to the root of your Google Drive (`MyDrive/`)

3. **Run the Notebook**
   - Execute cells sequentially
   - Cell 1 mounts Google Drive
   - Cell 2 extracts the dataset
   - Cell 3 runs the full training, evaluation, and saving pipeline

---

## 🏗️ Model Architecture

```
Sequential CNN Model:
├── Conv2D (32 filters, 3x3, ReLU)  — input: 128×128×3
├── MaxPooling2D (2x2)
├── Conv2D (64 filters, 3x3, ReLU)
├── MaxPooling2D (2x2)
├── Conv2D (128 filters, 3x3, ReLU)
├── MaxPooling2D (2x2)
├── Flatten
├── Dense (128 units, ReLU)
├── Dropout (0.5)
└── Dense (num_classes, Softmax)
```

**Hyperparameters:**

- Image Size: 128×128
- Batch Size: 32
- Epochs: 40
- Optimizer: Adam
- Loss: Categorical Crossentropy

---

## 📖 Usage

### Training the Model

1. Mount Google Drive and extract dataset (Cells 1–2)
2. Run the main training cell (Cell 3):
   - Splits dataset 70/15/15 (train/validation/test)
   - Loads and normalises images with `ImageDataGenerator`
   - Builds and trains the CNN model for 40 epochs
   - Evaluates on the test set
   - Generates confusion matrix and classification report
   - Visualises 8 sample predictions (green = correct, red = incorrect)
   - Saves model as `money_model_v3.h5` to Google Drive

### Making Predictions

- **Cell 4** – Download the saved model from Google Drive
- **Cell 5** – Upload any currency note image to get top-3 predictions with confidence percentages and a bar chart
- **Cell 6** – View test accuracy and loss as a bar chart
- **Cell 7** – View the prediction distribution histogram across all classes

---

## 📈 Model Performance

The model provides:

- **Accuracy/Loss Graphs**: Monitor training and validation metrics over 40 epochs
- **Confusion Matrix**: Heatmap of true vs. predicted labels on the test set
- **Classification Report**: Per-class precision, recall, and F1-score
- **Sample Predictions**: 8 images colour-coded green (correct) or red (incorrect)
- **Prediction Distribution**: Histogram showing how predictions are spread across classes

---

## 🛠️ Technologies Used

- **Python 3.x**
- **TensorFlow/Keras** — Deep learning framework
- **NumPy** — Numerical computing
- **Matplotlib** — Data visualization
- **Seaborn** — Statistical visualizations
- **Scikit-learn** — Metrics and evaluation
- **Google Colab** — Development environment

---

## 📁 Project Structure

```
ACNR (Automated Currency Note Recognition)/
├── ACNR_(Automated_Currency_Note_Recognition) v3.ipynb
├── README.md
└── Dataset/ (extracted from Drive)
    ├── dataset/         ← original class folders
    └── dataset_split/   ← auto-generated train/validation/test split
        ├── train/
        ├── validation/
        └── test/
```

---

## 🔮 Future Improvements

- [x] Add Dropout layer for regularization
- [x] Increase model depth (3 Conv blocks)
- [x] Train for more epochs (40)
- [x] Structured 70/15/15 dataset split
- [ ] Implement data augmentation (rotation, zoom, flip)
- [ ] Use learning rate scheduling / early stopping
- [ ] Implement transfer learning (VGG16, ResNet, MobileNet, etc.)
- [ ] Create standalone Python scripts for deployment
- [ ] Add real-time camera detection
- [ ] Export model to TensorFlow Lite for mobile deployment

---

## 👥 Contributors

- Lapalu Liyanage

---

## 📝 License

This project is created for educational purposes.

---

## 🙏 Acknowledgments

- Dataset contributors
- TensorFlow/Keras documentation
- Google Colab for providing free GPU resources

---

## 📧 Contact

For questions or suggestions, please open an issue in the repository.

---

**Version:** 3.0.0  
**Last Updated:** March 2026
