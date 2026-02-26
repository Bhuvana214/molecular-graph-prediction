# molecular-graph-prediction
Graph Neural Network for molecular toxicity prediction using Tox21 dataset (ROC-AUC ~0.76)

Overview

This project predicts molecular toxicity using a Graph Convolutional Network (GCN) trained on the Tox21 dataset.

Molecules are represented as graphs:

Atoms → Nodes

Bonds → Edges

The model learns structural patterns from molecular graphs to predict toxicity across 12 biological targets.

🔬 Dataset

This project uses the Tox21 dataset from MoleculeNet.

~8,000+ chemical compounds

12 toxicity prediction tasks

Multi-label classification

Some labels are missing (handled using masking)

The dataset is automatically downloaded when running the script:

dataset = MoleculeNet(root="data", name="Tox21")

The data is stored locally in the data/ folder and is not uploaded to GitHub.

🧠 Model Architecture

2-layer Graph Convolutional Network (GCN)

Global Mean Pooling for graph-level representation

Fully connected output layer

Multi-task prediction (12 outputs)

Loss Function:

BCEWithLogitsLoss (for multi-label classification)

📊 Evaluation Metric

Model performance is evaluated using:

ROC-AUC (Receiver Operating Characteristic - Area Under Curve)

ROC-AUC is preferred over accuracy for imbalanced scientific datasets.

🚀 Results

The model achieved:

Test ROC-AUC ≈ 0.76

using a simple 80/20 train-test split.

🛠️ Technologies Used

Python

PyTorch

PyTorch Geometric

Scikit-learn

NumPy
