# Structured Sparsification of LSTM Networks for Emotion Classification  
CS715 – Deep Learning Project  
University of Regina  

## 📌 Project Overview
This repository contains the implementation and experimental analysis for my CS715 project, inspired by the research paper:

**“Structured Sparsification of Gated Recurrent Neural Networks”**  
*Lobacheva, Chirkova, Markovich, Vetrov — AAAI 2020.*

The objective of this project is to:
1. Implement a baseline LSTM model for **emotion classification** using the Kaggle Emotion Dataset.  
2. Apply **weight-level global magnitude pruning** at multiple sparsity levels.  
3. Analyze the sparsity–performance trade-offs and compare insights to the principles introduced in structured sparsification literature.

The work demonstrates how LSTM models can retain strong predictive performance even under moderate sparsification, while also revealing task-specific sensitivity to higher sparsity levels.

---

## 📂 Repository Structure


📦 CS715_Structured_Sparsification <br />
├── CS715_Project_Base_LSTM_Model.ipynb # Baseline model training<br />
├── CS715_Project_Sparse_LSTM_Model.ipynb # Pruning experiments<br />
├── emotion_lstm_baseline.pt # Saved baseline model<br />
├── README.md # Project documentation<br />
├── train.txt # Training dataset<br />
├── val.txt # Validation dataset<br />
├── test.txt # Test dataset<br />

---

## 📊 Dataset  
The project uses the **Emotion Dataset** from Kaggle, which contains short text phrases annotated with one of six emotions:

- anger  
- fear  
- joy  
- love  
- sadness  
- surprise  

Train/validation/test split:
Train: 16,000 samples
Validation: 2,000 samples
Test: 2,000 samples


📌 **Dataset Link:**  
https://www.kaggle.com/datasets/parulpandey/emotion-dataset?select=test.csv

## ⚙️ Installation & Requirements

You can run the notebooks in **Google Colab** or your local machine with PyTorch installed.

Install required packages:

```bash
pip install torch torchvision torchaudio
pip install pandas numpy scikit-learn matplotlib
```

🚀 How to Run This Project <br>

1️⃣ Train the Baseline LSTM Model

Open: ```CS715_Project_Base_LSTM_Model.ipynb```

This notebook performs:
- Data preprocessing
- Vocabulary construction
- LSTM model creation
- Training using class-weighted cross-entropy
- Evaluation and saving the model checkpoint

Output:
```emotion_lstm_baseline.pt```

2️⃣ Structured Sparsification (Weight Pruning)

Open: ```CS715_Project_Sparse_LSTM_Model.ipynb```

This notebook:

- Loads the baseline model

- Applies global magnitude pruning at sparsity levels:```10%, 30%, 50%, 70%, 80%, 90%```

- Evaluates performance at each level

- Generates key figures such as:

    - Sparsity vs Accuracy Curve

    - Confusion Matrix

Example observed behavior:

- Accuracy remains stable up to 50% sparsity

- Accuracy collapses rapidly beyond 70% sparsity

This demonstrates the sensitivity of emotion classification to high weight sparsification.

📈 Example Results

- Baseline Test Accuracy: ~83%

- 50% Sparsity: ~81.1% accuracy

- 70% Sparsity: ~69.8% accuracy

- 90% Sparsity: ~34% accuracy

These results are consistent with findings in sparsification research, where moderate pruning acts as regularization but aggressive pruning destroys essential sequential dependencies.

📄 Original Research Paper (Not Included)

Due to copyright restrictions, the original AAAI paper is not included in this repository.

You may access it from the official link:

🔗 https://ojs.aaai.org/index.php/AAAI/article/view/5938

📜 Citation

If referencing this work or building on the sparsification concepts, cite the original authors:

```bash
Lobacheva, E., Chirkova, N., Markovich, A., & Vetrov, D. (2020). Structured sparsification of gated recurrent neural networks. 
Proceedings of the AAAI Conference on Artificial Intelligence, 34(04), 4989–4996.
```
🙏 Acknowledgment

This project was completed as part of CS715 – Advanced Topics in Deep Learning at the University of Regina.
I want to express my appreciation to Prof. JingTao Yao for providing the opportunity to explore deep learning concepts through this course project.
I also acknowledge the authors of the research papers that guided the theoretical understanding behind this work.

📬 Contact

Hemin Shah

Email: heminshah2001@gmail.com

LinkedIn: https://www.linkedin.com/in/hemin001

