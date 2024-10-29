Multi-Class Text Classification with Transformers
1. Overview
This project focuses on a multi-class text classification task using the 20 Newsgroups dataset, containing approximately 18,828 documents across 20 topics. Our goal is to leverage DistilBERT to classify text into these categories effectively.

2. Dataset and Preprocessing
Dataset: 20 Newsgroups, covering topics like sports, religion, science, etc.
Data Preparation:
Tokenization: DistilBERT tokenizer encodes text, handles padding/truncation, and converts to tensors.
Data Loading: Data is loaded using PyTorch’s TensorDataset and DataLoader.
3. Model Architecture
Base Model: DistilBERT, chosen for its efficiency.
Self-Attention: Utilizes Queries (Q), Keys (K), and Values (V) for attention mechanism.
Final Model Layers:
Embeddings with layer normalization and dropout.
Transformer blocks with multi-head self-attention.
Classification head for outputting logits per class.
4. Training and Hyperparameter Optimization
Data Splitting: Train (70%), Validation (10%), Test (20%).
Hyperparameter Tuning: Conducted using Optuna on:
Learning rate, batch size, weight decay, warmup steps, and dropout rate.
Early Stopping: Stops training if no improvement in validation accuracy.
5. Results
Best Validation Accuracy: 92.82%
Test Metrics:
Accuracy: 92.03%
Precision: 92.01%
Recall: 91.91%
F1 Score: 91.95%
ROC-AUC: 99.16%
6. Model Evaluation and Performance
Detailed Class-by-Class Analysis:
High-performing classes: rec.sport.hockey, sci.crypt.
Moderate classes: comp.sys.ibm.pc.hardware.
Lower scores for talk.religion.misc.
7. Comparison with Hugging Face Model
Achieved comparable performance to the Hugging Face model, confirming the effectiveness of the custom approach with Optuna fine-tuning.

8. Testing with New Sentences
Example predictions:

"Ford came out with a new hybrid engine model." → rec.autos
"Advancements in AI technology are rapidly changing the industry." → comp.sys.mac.hardware







