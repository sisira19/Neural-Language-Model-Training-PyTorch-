# Neural-Language-Model-Training-PyTorch-
# IIIT Hyderabad – Assignment 2  
## Neural Language Model Training (PyTorch)

### 📘 Objective  
Train a Neural Language Model from scratch using PyTorch to understand how model architecture and training affect text prediction and perplexity.

---

### 🧾 Dataset  
**Dataset:** *Pride and Prejudice – Jane Austen* (provided by IIIT Hyderabad)  
- Total characters: ~711k  
- Vocabulary size: 3,164 (after min_freq=3)  
- Train/validation split: 90/10  

---

### ⚙️ Implementation Overview  
**Architecture:** 2-layer LSTM Language Model  
- Embedding size: 128  
- Hidden size: 256  
- Dropout: 0.3  
- Sequence length: 30  
- Batch size: 64  
- Optimizer: Adam (lr=0.001)  
- Loss: CrossEntropyLoss  
- Metric: Perplexity (PPL)

---

### 🧠 Experiments  
| Model Type | Configuration | Epochs | Observation |
|-------------|---------------|---------|--------------|
| **Underfit** | Small LSTM (64 hidden, 1 layer) | 2 | High loss, flat curves |
| **Overfit** | Large LSTM (512 hidden, 3 layers, no dropout) | 10 | Low train loss, high val loss |
| **Best-fit** | Medium LSTM (256 hidden, 2 layers, dropout=0.3) | 5 | Balanced train/val losses |

---

### 📊 Results Summary  
| Model | Train Loss | Val Loss | Val PPL | Remarks |
|--------|-------------|-----------|----------|----------|
| Underfit | ~5.8 | ~5.9 | ~365 | Small capacity |
| Overfit | ~3.9 | ~5.6 | ~270 | Memorization observed |
| Best-fit | ~4.2 | ~5.3 | ~200 | Best generalization |

---

### 💬 Sample Generated Text (Best-fit Model)
Elizabeth was a great deal of the room and the first of the room and the first of the room and the first of the room...


> The model demonstrates structural learning and repetition typical of early-epoch LSTMs. Longer training reduced `<unk>` tokens and improved fluency.

---
## 📁 Folder Structure

```
IIIT_Assignment2/
├── data/
│   └── Pride_and_Prejudice-Jane_Austen.txt
├── src/
│   ├── data_utils.py
│   ├── model.py
│   └── train.py
├── results/
│   ├── loss_plot.png
│   ├── model_best.pth
│   ├── model_bestfit_long.pth
│   ├── model_bestfit.pth
│   ├── model_overfit.pth
│   └── model_underfit.pth
├── notebooks/
│   └── assignment2.ipynb
└── Assignment_report.pdf
```

```




---

### 🚀 How to Run
1. Clone the repository and install dependencies:
   ```bash
   pip install torch matplotlib tqdm
2. Ensure dataset is placed inside data/.

3. Run the training:
python src/train.py

4.View results and plots in the results/ folder.
