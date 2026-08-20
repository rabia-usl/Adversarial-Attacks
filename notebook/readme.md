# Adversarial Attacks and Defenses on CNNs

This repository contains a Deep Learning term project focused on analyzing the robustness of Convolutional Neural Networks (CNNs) against various adversarial attacks and evaluating different defense mechanisms. 

The project uses the CIFAR-10 dataset and explores how subtle perturbations can fool neural networks, as well as how to make these models more resilient.

## 📌 Project Overview
* **Dataset:** CIFAR-10
* **Framework:** PyTorch
* **Key Focus:** White-box/Black-box attacks, Attack Transferability, and Defense Trade-offs.

## 🚀 Features & Implementation

### 1. Adversarial Attacks
The project explores generating adversarial examples using the `torchattacks` library. We evaluate the models under different magnitudes of perturbations ($\epsilon$):
* **FGSM (Fast Gradient Sign Method):** A fast, gradient-based one-step attack.
* **PGD (Projected Gradient Descent):** A powerful, iterative multi-step attack.
* **C&W (Carlini & Wagner):** An optimization-based attack aiming for minimal visible perturbation.

### 2. Defense Mechanisms
To counter these attacks, multiple defense strategies were implemented and compared to understand the trade-off between clean accuracy and adversarial robustness:
* **Adversarial Training:** Training the model explicitly with adversarial examples.
* **Input Preprocessing (Gaussian Blur):** Smoothing out high-frequency adversarial noise before feeding the image to the model.
* **Feature Squeezing:** Reducing the color bit depth of the images to eliminate subtle, pixel-level perturbations.

### 3. Transferability Analysis
* **Black-box Transferability:** Evaluated how well adversarial examples generated on a source model (`SimpleCNN`) transfer to a different target architecture (`DeeperCNN`) without accessing the target model's gradients.

## 🛠️ Technologies & Libraries
* **Python**
* **PyTorch & Torchvision**
* **Torchattacks** (for adversarial attack implementations)
* **NumPy, Matplotlib, Seaborn** (for data manipulation and visualization)
* **Scikit-learn** (for confusion matrix metrics)

## 📊 Visualizations and Analysis
The notebook includes detailed visual analyses:
* Accuracy vs. Epsilon graphs comparing Normal and Robust models.
* Visual comparisons of *Original*, *Perturbation*, and *Adversarial* images.
* Confusion matrices comparing model predictions on clean data vs. data under attack.
* Detailed tradeoff analysis charts for each defense method.

## ⚙️ How to Run
1. Clone this repository.
2. Install the required dependencies: `pip install torch torchvision torchattacks matplotlib seaborn scikit-learn`
3. Run the Jupyter Notebook cell by cell. Ensure you have a GPU enabled (e.g., on Google Colab or local CUDA environment) for faster training and attack generation.
