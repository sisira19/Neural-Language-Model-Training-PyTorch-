# Neural Language Model Training (PyTorch)

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

### 🚀 How to Run
1. Clone the repository and install dependencies:
   ```bash
   pip install torch matplotlib tqdm
2. Ensure dataset is placed inside data/.

3. Run the training:
python src/train.py

4.View results and plots in the results/ folder.

## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/sisira19/Neural-Language-Model-Training-PyTorch-.git
cd Neural-Language-Model-Training-PyTorch-
```

### 2️⃣ Install Dependencies
```bash
pip install torch numpy matplotlib tqdm
```

---

## 🏋️‍♂️ Training Instructions

Run training for different configurations:

### **Underfit**
```bash
python src/train.py --config underfit
```

### **Overfit**
```bash
python src/train.py --config overfit
```

### **Best-fit**
```bash
python src/train.py --config bestfit
```

The script will:

✔️ Load dataset  
✔️ Train the model  
✔️ Save weights to `results/`  
✔️ Save loss plots  

---

## 🧪 Text Generation (Inference)

Use a trained model to generate text:

```bash
python src/train.py --generate --model_path results/model_bestfit.pth
```

---

## 🔗 Download Trained Models (Google Drive)

All trained models are available in a public Google Drive folder:

📁 **Google Drive (Models + Results):**  
https://drive.google.com/drive/folders/15Dvyty1zYdVIHajjTq-6R2A-5SJqzCkc?usp=drive_link

This includes:

- `model_underfit.pth`  
- `model_overfit.pth`  
- `model_bestfit.pth`  
- Additional experimental files  
- Loss plots  

---

## 📊 Results Summary

The `results/` folder includes:

- `loss_plot.png` — combined loss visualization  
- Underfit / Overfit / Best-fit model weights  
- Trained model variants (`best`, `bestfit_long`)  

These plots help compare convergence behavior and model quality.

---

## ⭐ Extra Credit Work

This project includes:

- Multiple model experiments  
- Proper training pipeline  
- Organized code structure  
- Loss visualizations  
- Reproducible results  
- Additional long-training best-fit model (`model_bestfit_long.pth`)  

---

## 👨‍💻 Author
**Sisira**
