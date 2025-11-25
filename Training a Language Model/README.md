# Training a Tiny Transformer Language Model (ELI5 Dataset)

This project implements a **decoder-only Transformer language model** trained from scratch on a processed subset of the **ELI5** dataset.  
The goal is to reproduce a GPT-style autoregressive language model and evaluate it based on **perplexity (PPL)**.

---

## Project Structure
Training a Language Model
├── colab_test.ipynb # Notebook for running and validating the .py script
├── logits.npy # Saved test logits for PPL evaluation
├── script.py # Main training script (model, training loop, logits saving)
└── test_lm.py # Evaluation script provided by TA

---

## Training Configuration

| Setting | Value |
|--------|--------|
| **Optimizer** | AdamW |
| **Learning Rate** | 5e-4 |
| **Weight Decay** | 0 |
| **Loss Function** | CrossEntropyLoss |
| **Epochs** | 5 |
| **Batch Size** | 32 |
| **Dataset** | ELI5 (dany0407/eli5_category) |
| **Tokenization** | GPT-2 tokenizer |

---

## 📊 Results

| Metric | Value |
|--------|--------|
| **Best Test Perplexity** | **286** ✅ |
| **Baseline Perplexity** | 390 |
| **Improvement** | **−26.7%** |
| Test Logits Shape | (75, 200, 50257) |
| Saved Logits | `logits.npy` |

