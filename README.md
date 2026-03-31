# GSoC 2026 | ML4SCI: NeuroDyads Pre-task Solution
## Project: Decoding Inter-Brain Manifolds of Conversational Affect

This repository contains the technical implementation and scientific report for the **NeuroDyads** pre-task as part of the Google Summer of Code 2026 application for the **ML4SCI (Machine Learning for Science)** organization.

---

### 📌 Project Overview
The goal of this project is to decode emotional affect (positive vs. negative) from 128-channel dyadic EEG data. Using a combination of signal processing and state-of-the-art contrastive learning (**CEBRA**), this pipeline isolates neural manifolds that serve as mathematical signatures for social affect.

### 🛠️ Technical Pipeline
1. **Preprocessing & ICA:** - Band-pass filtering (1–40 Hz).
   - **Independent Component Analysis (ICA)** to remove eye blinks and muscle noise while preserving cortical Alpha rhythms.
2. **Manifold Learning (CEBRA):** - Projecting high-dimensional EEG signals into a **3D latent space**.
   - Optimizing InfoNCE loss over 2,000 iterations.
3. **Decoding & Validation:** - Using a **k-Nearest Neighbors (k-NN)** decoder for classification.
   - Validation against a **shuffled-label control model**.

### 📊 Key Results
| Metric | Main Model | Control (Shuffled) |
| :--- | :--- | :--- |
| **k-NN Accuracy** | **59.29%** | **49.43%** |
| **Performance Gain** | **~10%** | **Baseline** |

> **Interpretation:** The 10% jump over the control baseline validates that the model successfully captured biological neural manifolds rather than stochastic noise.

---

### 📂 Repository Structure
* `main.ipynb`: Full implementation (Preprocessing, ICA, CEBRA, KNN).
* `requirements.txt`: Necessary libraries (MNE, CEBRA, PyTorch).
* `README.md`: Project documentation.

### 👤 About the Candidate
**Shambhavi Sinha**
* **Education:** 2nd Year B.Tech CSE Undergraduate.
* **Portfolio Highlights:** - Lead Developer of **VitalChain** (offline-first mesh network).
  - 2nd Place Winner, **IEEE AESS Hackathon** (Autonomous Multi-Agent Coordination).
  - Design Associate at **AWS Cloud Club**.
