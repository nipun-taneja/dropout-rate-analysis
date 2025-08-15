# Dropout Rate Experiments on MNIST, Fashion MNIST, and CIFAR-10

Checking how varying **dropout rates** impact the performance of fully connected neural networks across three benchmark datasets: **MNIST**, **Fashion MNIST**, and **CIFAR-10**.

---

## Objective
- Compare the effect of dropout rates on model accuracy and generalization.  
- Identify optimal dropout ranges for different datasets.  
- Derive practical guidelines for choosing dropout when training neural networks.  

---

## Methodology
1. Datasets:
   - **MNIST** – handwritten digits (28×28 grayscale).  
   - **Fashion MNIST** – clothing categories (28×28 grayscale).  
   - **CIFAR-10** – objects & animals (32×32 RGB).  

2. Experiment Setup:
   - Fully connected neural network.  
   - Dropout rates tested:  
     `{0.0, 0.1, 0.3, 0.5, 0.6, 0.7, 0.8, 0.9, 0.91, 0.93, 0.95, 0.97, 0.99}`  
   - Training: 10 epochs per configuration.  

3. Metrics:
   - Validation Accuracy vs. Epochs.  
   - Test Accuracy vs. Dropout Rates.  

---

## Results

### MNIST
*Moderate dropout improves generalization; too high dropout reduces learning capacity.*  
Optimal dropout ≈ **0.3** → Test Accuracy ~ **98.3%**  
<img width=45% height="547" alt="image" src="https://github.com/user-attachments/assets/d47bc5ba-3a8e-4e2c-bce5-3dcacd1d0428" />
<img width=45% height="547" alt="image" src="https://github.com/user-attachments/assets/f63b7f73-3883-4d24-91e5-4a29e998464f" />

---

### Fashion MNIST
*Higher dropout needed compared to MNIST; stabilizes variance in this more complex dataset.*  
Optimal dropout ≈ **0.5** → Test Accuracy ~ **89.8%**  
<img width=45% height="547" alt="image" src="https://github.com/user-attachments/assets/25b21548-f0a1-4534-9dba-290e6bfdc68f" />
<img width=45% height="547" alt="image" src="https://github.com/user-attachments/assets/df85c11d-5fe7-4f84-8a20-810b3b6faaeb" />

---

### CIFAR-10
*CIFAR-10 is most sensitive to very high dropout (>0.9), where performance collapses.*  
Optimal dropout ≈ **0.5–0.6** → Test Accuracy ~ **59.2%**  
<img width=45% height="547" alt="image" src="https://github.com/user-attachments/assets/235b096f-398d-4bad-9610-444472e044c9" />
<img width=45% height="547" alt="image" src="https://github.com/user-attachments/assets/a2b80bd0-ef70-4c4f-8cde-cfce0786b86a" />

---

## Key Insights
- **Optimal dropout depends on dataset complexity**:  
  - MNIST: simple → lower dropout (0.3) works best.  
  - Fashion MNIST: moderately complex → higher dropout (0.5).  
  - CIFAR-10: high complexity → dropout helps up to a point (0.5–0.6), but extreme dropout destroys performance.  
- **High dropout (>0.9)**: Most harmful on CIFAR-10, less so on MNIST.  
- **Guideline**: Start with 0.3–0.5 dropout for fully connected layers, adjust by dataset complexity.  

---

## How to Run
Run in **Google Colab**:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nipun-taneja/dropout-rate-analysis/blob/main/Dropout_Experiments.ipynb)

---

## ✍️ Author
Nipun Taneja – MS in Artificial Intelligence @ SFSU  
[LinkedIn](https://www.linkedin.com/in/nipun-taneja) | [GitHub](https://github.com/nipun-taneja)
