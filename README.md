# Handwritten Digit Recognition using CNN (MNIST)

This project implements a complete **Convolutional Neural Network (CNN)** image classification pipeline using **PyTorch**, trained on the **MNIST** dataset and evaluated on both the standard test set and real-world handwritten digit images (captured using a smartphone).  
The goal is to build a model capable of accurately recognizing digits (0–9) from 28×28 grayscale images.


## Dataset

- **Standard Dataset:** MNIST (60,000 training images, 10,000 test images)
- Classes Used:
  0, 1, 2, 3, 4, 5, 6, 7, 8, 9
- Custom Dataset:
  Real-world handwritten digit images captured by MAYA stored in `assets/`.





## Model Architecture

The model is a simple CNN built using `torch.nn.Module`.

**Key Layers:**
- Convolution (3×3) + ReLU Activation  
- MaxPooling (2×2)  
- Fully Connected Layers  
- Output layer (10 classes)

##  Training Process

- Dataset automatically downloaded using `torchvision.datasets`
- Images preprocessed with normalization and resizing
- Model trained for **10 epochs**
- Training loss and accuracy plotted per epoch

### **Training Results**
Epoch 1/10 - Loss: 0.1346, Accuracy: 95.92%
Epoch 2/10 - Loss: 0.0410, Accuracy: 98.77%
Epoch 3/10 - Loss: 0.0260, Accuracy: 99.17%
Epoch 4/10 - Loss: 0.0174, Accuracy: 99.43%
Epoch 5/10 - Loss: 0.0134, Accuracy: 99.54%
Epoch 6/10 - Loss: 0.0104, Accuracy: 99.63%
Epoch 7/10 - Loss: 0.0071, Accuracy: 99.77%
Epoch 8/10 - Loss: 0.0070, Accuracy: 99.75%
Epoch 9/10 - Loss: 0.0063, Accuracy: 99.83%
Epoch 10/10 - Loss: 0.0053, Accuracy: 99.83%


**Observations**
- Training loss decreases steadily across epochs  
- Accuracy improves consistently and stabilizes around **99.8%**

### **Confusion Matrix**

A confusion matrix was generated on the MNIST test dataset to analyze per-class performance.

<img width="1019" height="714" alt="Screenshot 2025-12-26 013007" src="https://github.com/user-attachments/assets/7f0a59ff-5251-4a02-b7ef-dae2d8b52428" />



**Key Observations**
- Strong recognition for all digits (0–9)
- Occasional confusion between similar digits (e.g., 3 and 8)
- Overall high precision and recall across all classes

##  Visual Error Analysis

Misclassified samples from the MNIST test set were visualized to understand model limitations.

<img width="1356" height="546" alt="Screenshot 2025-12-26 013019" src="https://github.com/user-attachments/assets/16c53612-48c0-4c5a-9d68-96f79239fd84" />



**Findings**
- Misclassifications often occur on poorly written digits or images with unusual stroke patterns.


## Real-World Image Predictions

The trained model was evaluated on real handwritten images located in the `assets/` folder.

For each image, the model outputs the **predicted digit** and **confidence score**.



**Example Output:**

<img width="1203" height="512" alt="Screenshot 2025-12-26 013027" src="https://github.com/user-attachments/assets/b1e0bc5b-245d-49d9-b3d6-553525177eca" />


eight.jpeg → Predicted: 8 (Confidence: 37.35%)
five.jpeg → Predicted: 3 (Confidence: 59.90%)
one.jpeg → Predicted: 2 (Confidence: 66.46%)


**Observations**
- Predictions are influenced by background noise, alignment, and lighting.
- Performance on smartphone images shows the model’s generalization capability.
