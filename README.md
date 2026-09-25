# Graph-Contrastive Learning for Self-Supervised Intrusion Detection Systems (IDS)

This repository contains the implementation of a Self-Supervised Intrusion Detection System (IDS) built using Graph-Contrastive Learning (GCL). By leveraging graph neural networks (GNNs) and contrastive learning paradigms, this model learns robust representations of network traffic data without relying heavily on labeled anomalous samples, making it ideal for detecting novel or zero-day cyber attacks.

---

## Features

- **Graph Representation of Network Traffic:** Transforms tabular or flow-based network data into graph structures to capture complex topological relationships and packet-to-packet dependencies.
- **Self-Supervised Pre-training:** Utilizes graph-contrastive learning to maximize agreement between differently augmented views of network subgraphs, enabling the model to learn meaningful representations from unlabeled data.
- **Anomaly Detection & Classification:** Employs learned embeddings for downstream intrusion detection tasks, effectively flagging malicious anomalies in network environments.
- **Jupyter Notebook Implementation:** Easy-to-follow interactive workflow for data preprocessing, graph construction, model training, and evaluation.

---

## Project Structure

```text
├── gcl_ids_notebook.ipynb      # Main Jupyter Notebook containing the end-to-end pipeline
├── requirements.txt            # Python dependencies
└── README.md                   # Project documentation
```

---

## Prerequisites & Dependencies

To run the notebook successfully, ensure you have Python 3.8+ installed along with PyTorch and PyTorch Geometric (PyG).

### Key Libraries:
- `torch`
- `torch-geometric`
- `numpy`
- `pandas`
- `scikit-learn`
- `networkx`
- `matplotlib`

---

## Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/graph-contrastive-ids.git
   cd graph-contrastive-ids
   ```

2. **Install the dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
   *(Note: Ensure you install the correct version of PyTorch Geometric matching your PyTorch and CUDA versions).*

3. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook gcl_ids_notebook.ipynb
   ```

---

## How It Works

1. **Data Preprocessing:** Network flow records are cleaned, normalized, and converted into graph structures where nodes represent network entities/flows and edges represent behavioral interactions.
2. **Data Augmentation:** Stochastic graph augmentations (such as node feature masking or edge dropping) are applied to generate dual views of the graph.
3. **Contrastive Objective:** The GNN encoder maps the augmented graphs into latent embeddings, optimized via a contrastive loss function (e.g., InfoNCE loss) denoted as:
   $$\mathcal{L} = -\log \frac{\exp(\text{sim}(z_i, z_j)/\tau)}{\sum_{k} \exp(\text{sim}(z_i, z_k)/\tau)}$$
4. **Evaluation:** The learned representations are evaluated on their capacity to separate normal traffic profiles from intrusive anomalies.

---

## Dataset

This project is compatible with standard network intrusion datasets formatted into graph representations, such as:
- **NSL-KDD** / **KDD Cup 99**
- **CIC-IDS2017** / **CICIDS2018**
- **UNSW-NB15**

*Make sure to place your dataset in the appropriate directory as specified in the notebook configuration.*

---

## Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [![Issues](https://img.shields.io/github/issues/gaurkumarsoni/Graph-Contrastive-Learning_Based_Self-Supervised_IDS)](https://github.com/username/repository-name/issues).

---
