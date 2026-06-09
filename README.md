# 🧠 NeuroAI — Alzheimer's Disease Diagnostic System

> An AI-powered diagnostic platform for Alzheimer's disease staging using **MRI image classification**, **Knowledge Graphs**, and **Generative AI**.

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red?style=flat-square&logo=pytorch)
![Neo4j](https://img.shields.io/badge/Neo4j-Knowledge%20Graph-green?style=flat-square&logo=neo4j)
![LangChain](https://img.shields.io/badge/LangChain-GPT--4.1-blueviolet?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

---

## 📌 Overview

NeuroAI is a Final Year Project (FYP) that combines **Deep Learning**, **Knowledge Graphs**, and **Large Language Models** to assist in the early diagnosis and staging of Alzheimer's disease from brain MRI scans.

The system has two core modules:

| Module | Description |
|--------|-------------|
| **Deep Learning Module** | Classifies Alzheimer's dementia stages from MRI scans using Vision Transformers (ViT) and CNNs |
| **Knowledge Graph + GenAI Module** | Provides explainable diagnostic reports by querying a Neo4j medical knowledge graph via LangChain and GPT-4.1 |

---

## 🎯 Problem Statement

Alzheimer's disease affects millions globally, yet early diagnosis remains a challenge due to:
- Subjective interpretation of MRI scans
- Lack of explainability in AI diagnostic tools
- Disconnected medical knowledge sources

NeuroAI addresses these gaps by combining image-based classification with ontology-driven reasoning and natural language explanation.

---

## 🗂️ Dataset

MRI scans are classified into **4 dementia stages**:

```
FYP/
├── Non Demented/           # Cognitively normal
├── Very Mild Dementia/     # Early-stage cognitive decline
├── Mild Dementia/          # Moderate cognitive impairment
└── Moderate Dementia/      # Advanced Alzheimer's staging
```

- Source: [Alzheimer's MRI Dataset — Kaggle](https://www.kaggle.com/datasets/tourist55/alzheimers-dataset-4-class-of-images)
- 4 classes, multiclass classification task
- Preprocessing: resizing, normalization, augmentation

---

## 🏗️ System Architecture

```
MRI Scan Input
      │
      ▼
┌─────────────────────┐        ┌──────────────────────────────┐
│  Deep Learning      │        │  Knowledge Graph + GenAI     │
│  ─────────────────  │        │  ──────────────────────────  │
│  Vision Transformer │        │  Neo4j Knowledge Graph       │
│  (ViT) / CNN        │──────▶│  (ADO + RadLex Ontologies)   │
│                     │        │           │                   │
│  PyTorch · OpenCV   │        │      LangChain + GPT-4.1     │
└─────────────────────┘        │           │                   │
                                │  Explainable Diagnostic      │
                                │  Report + Recommendations    │
                                └──────────────────────────────┘
                                           │
                                           ▼
                                   Flask Web App
                              (Upload MRI → Get Diagnosis)
```

---

## ⚙️ Tech Stack

### Deep Learning
- **PyTorch** — model training and inference
- **Vision Transformer (ViT)** — primary classification architecture
- **CNN** — comparative baseline model
- **OpenCV / NumPy / Pandas** — image preprocessing and augmentation
- **Scikit-Learn** — evaluation metrics

### Knowledge Graph & Generative AI
- **Neo4j** — graph database for medical knowledge
- **Cypher Query Language** — graph traversal and retrieval
- **ADO (Alzheimer's Disease Ontology)** — domain knowledge representation
- **RadLex Ontology** — radiology terminology
- **LangChain** — LLM orchestration and GraphCypherQAChain
- **GPT-4.1** — natural language report generation
- **GraphRAG** — grounded AI responses from graph knowledge

### Web Application
- **Flask** — backend REST API
- **HTML / Jinja2 / Bootstrap** — frontend interface
- **Postman** — API testing

---

## 📁 Repository Structure

```
FYP/
├── Mild Dementia/              # MRI dataset — mild stage
├── Moderate Dementia/          # MRI dataset — moderate stage
├── Non Demented/               # MRI dataset — no dementia
├── Very Mild Dementia/         # MRI dataset — very mild stage
├── Backend.ipynb               # Main notebook: model training, KG integration, inference
├── index.html                  # Web app — MRI upload page
├── result.html                 # Web app — diagnosis result page
└── Documentation.pdf           # Full FYP documentation
```

---

## 🚀 Getting Started

### Prerequisites

```bash
Python 3.10+
Neo4j Desktop or AuraDB (free tier)
OpenAI API Key (for GPT-4.1)
```

### Installation

```bash
# Clone the repository
git clone https://github.com/IshaTariq-993/FYP.git
cd FYP

# Install dependencies
pip install torch torchvision transformers opencv-python pandas numpy scikit-learn
pip install flask langchain langchain-community neo4j openai
pip install matplotlib seaborn jupyter
```

### Neo4j Setup

1. Download and install [Neo4j Desktop](https://neo4j.com/download/)
2. Create a new database
3. Load the ADO and RadLex ontology files
4. Update the connection credentials in `Backend.ipynb`

### Run the Notebook

```bash
jupyter notebook Backend.ipynb
```

### Run the Web App

```bash
python app.py
# Navigate to http://localhost:5000
```

---

## 📊 Model Performance

Class                    Precision    Recall    F1 Score

Mild Dementia            81.5%        91.6%     86.2%
Moderate Dementia        76.0%        79.2%     77.6%
Very Mild Dementia       100.0%       83.3%     90.9%
Non-Demented             100.0%       100.0%    100.0%

Macro Average            89.4%        88.5%     88.7%

---

## 🔬 Key Features

- ✅ **Multiclass MRI Classification** — 4-stage Alzheimer's dementia staging
- ✅ **Explainable AI** — ontology-driven reasoning explains every diagnosis
- ✅ **Natural Language Reports** — GPT-4.1 generates human-readable diagnostic summaries
- ✅ **Knowledge Graph Querying** — ask medical questions in plain English via GraphCypherQAChain
- ✅ **Full-Stack Web App** — upload an MRI scan and get a complete diagnostic report
- ✅ **GraphRAG** — AI responses grounded in structured medical knowledge

---

## 📄 Documentation

Full project documentation is available in [`Documentation.pdf`](./Documentation.pdf), covering:
- System design and architecture
- Dataset description and preprocessing
- Model training and evaluation
- Knowledge graph design
- Results and analysis

---

## 👩‍💻 Author

**Isha Tariq**
Machine Learning Engineer | AI Developer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat-square&logo=linkedin)](www.linkedin.com/in/isha-tariq-356384406)
[![GitHub](https://img.shields.io/badge/GitHub-IshaTariq--993-black?style=flat-square&logo=github)](https://github.com/IshaTariq-993)

---


---

## 🙏 Acknowledgements

- Alzheimer's Disease Ontology (ADO) — open-source medical ontology
- RadLex — radiology ontology by RSNA
- Kaggle Alzheimer's MRI Dataset
- University of Sargodha — Department of Computer Science
