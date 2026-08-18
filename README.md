

# Tic-Tac-Toe Symbol Classifier (CNN)

A Deep Learning project built with **PyTorch** that uses a Convolutional Neural Network (CNN) to recognize and classify Tic-Tac-Toe board symbols from images.

![CNN Architecture](https://images.squarespace-cdn.com/content/v1/5e417305686d8a11f786eb86/1581515207283-JDIIO1XO8ONYJYSIWKB0/nnvis.png?format=1000w)

---



## 📌 Project Overview

This project classifies **128x128 grayscale images** into three categories:

* **Blank**: An empty square.
* **Circle**: Representing the 'O' player.
* **Nought**: Representing the 'X' player.

The custom CNN uses **Batch Normalization** and **Dropout** to improve performance and reduce overfitting.

---

## 🚀 Features

* **Custom CNN Architecture**: 3 convolutional layers + 3 fully connected layers.
* **Data Augmentation**: Random vertical flips and rotations to make the model robust.
* **High Performance**: Achieved ~98% training accuracy and ~94% test accuracy.
* **GPU Support**: Runs on CUDA-enabled devices for faster training.

---

## 🛠️ Tech Stack

* **Framework**: PyTorch
* **Data Handling**: Torchvision, DataLoader
* **Evaluation**: Scikit-learn (Confusion Matrix, Classification Report)
* **Language**: Python

---

## 📂 Project Structure

```
.
├── images/
│   ├── train/          # 480 images (Blank, Circle, Nought)
│   └── test/           # 120 images (Blank, Circle, Nought)
├── Tic_Tac_Toe_CNN_v1.ipynb  # Main notebook with training & evaluation
└── README.md
```

---

## 🏗️ Model Architecture

**CustomCNN** consists of:

1. **Conv Layer 1**: 1 → 16 channels, BatchNorm, ReLU, MaxPool
2. **Conv Layer 2**: 16 → 32 channels, BatchNorm, ReLU, MaxPool
3. **Conv Layer 3**: 32 → 64 channels, ReLU, MaxPool
4. **Fully Connected Layers**: 256 → 128 → 3 units (Output)
5. **Regularization**: Dropout (0.5)

---

## 📈 Results

Trained for **15 epochs** using **AdamW optimizer**:

| Metric   | Training | Testing |
| -------- | -------- | ------- |
| Accuracy | 98.3%    | 93.3%   |
| Loss     | 0.0503   | -       |

### Classification Report (Test Set)

```text
              precision    recall  f1-score   support
       blank       1.00      1.00      1.00        40
      circle       0.85      1.00      0.92        40
       nought      1.00      0.82      0.90        40
```

---

## 🔄 Data Augmentation

* **Random Vertical Flip**: Helps the model recognize symbols even if images are flipped vertically.
* **Random Rotation (±20°)**: Makes the network robust to slight rotations in the Tic-Tac-Toe board.

These augmentations reduce overfitting and improve generalization to unseen images.

---

## ⚙️ How to Run

1. **Clone the repo**:

```bash
git clone https://github.com/your-username/tic-tac-toe-cnn.git
cd tic-tac-toe-cnn
```

2. **Install Dependencies**:

```bash
pip install torch torchvision numpy scikit-learn
```

3. **Update Paths**:
   Edit the `ImageFolder` paths in the notebook to point to your local dataset directory.

4. **Run the Notebook**:
   Open `Tic_Tac_Toe_CNN_v1.ipynb` in Jupyter or VS Code and run all cells.

---

## 📄 License

This project is open-source and available under the **MIT License**.
