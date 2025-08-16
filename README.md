# deep-learning-text-classification
## Deep Learning Architectures for Text Classification on AG News Dataset

## 📌 Overview

This project presents a comprehensive evaluation of various deep learning architectures for text classification, focusing on the AG News dataset. The study investigates the impact of preprocessing techniques, model structures, and embedding strategies on classification accuracy, training efficiency, and generalization performance.

📌 Key architectures explored include:

- Dense Neural Networks (DNN)
- Recurrent Neural Networks (RNN)
- Long Short-Term Memory Networks (LSTM)
- One-Dimensional Convolutional Neural Networks (1D CNN)

Pretrained GloVe embeddings were employed, and comparisons were made against learnable embeddings to assess their effect on model performance.

---

## 📌 Research Objectives

- Evaluate the effect of vocabulary size, stopword removal, and sequence length on model performance.
- Benchmark multiple deep learning architectures for text classification accuracy and training efficiency.
- Compare pretrained embeddings with learnable embeddings to understand their impact on generalization.
- Propose a conceptual framework for future generative language models based on deep sequence architectures.

---

## 📌 Dataset

The AG News dataset consists of 4 balanced categories of news articles:  
- World  
- Sports  
- Business  
- Science/Technology  

Each category contains approximately 30,000 training samples and 1,900 test samples.

---

## 📌 Methodology

- **Preprocessing:** Vocabulary sizes of 5,000, 10,000, and 20,000 tested; stopword removal applied; sequences padded/truncated to fixed length of 128 tokens.
- **Baseline Model:** Dense Neural Network evaluated across 12 configurations to identify optimal preprocessing parameters.
- **Advanced Models:** RNN, LSTM (uni- and bi-directional), and 1D CNN trained using optimal preprocessing setup with GloVe embeddings.
- **Embedding Comparison:** Best-performing model retrained with learnable embeddings to evaluate generalization capabilities.

---

## 📌 Results Summary

| Model                  | Test Accuracy | Training Time (seconds) | Notes                                      |
|------------------------|---------------|------------------------|--------------------------------------------|
| Dense Neural Network    | ~Baseline     | Moderate               | Baseline for preprocessing selection       |
| Unidirectional RNN     | Poor          | Moderate               | Underfitting, memorized dominant class     |
| Bidirectional RNN      | 0.88          | ~313                   | Significant improvement over unidirectional|
| Unidirectional LSTM    | 0.89          | ~625                   | Strong performance with long-range context |
| Bidirectional LSTM     | **0.91**      | 1110                   | Highest accuracy, high computational cost  |
| 1D CNN                 | 0.91          | 408                    | Balanced accuracy and efficiency            |

- Pretrained GloVe embeddings outperformed learnable embeddings in generalization.
- 1D CNN selected as the best model balancing accuracy and training efficiency.

---

## 📌 Usage

### Environment Setup

```bash
# Create virtual environment
python -m venv env
source env/bin/activate  # On Windows use `env\Scripts\activate`

# Install dependencies
pip install -r requirements.txt
