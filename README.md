# XAI-APT-LLMs

## Explainable LLM-Based Advanced Persistent Threat Detection

This repository contains the implementation and experimental work for **XAI-APT**, a framework for detecting Advanced Persistent Threats (APTs) from system logs using Large Language Model (LLM) embeddings, autoencoder-based anomaly detection, and explainable AI (XAI).

The project investigates how semantic representations from LLMs can be combined with reconstruction-based anomaly detection to identify suspicious system activities associated with cyber APTs.

## Project Overview

Advanced Persistent Threats are difficult to detect because attackers can perform a sequence of legitimate-looking activities over a long period of time. Traditional signature-based approaches may struggle to identify these behaviors.

This project uses a two-stage approach:

1. **LLM-based log representation**

   * System logs are converted into semantic embeddings using different language models.
   * The embeddings capture contextual and semantic information from the log events.

2. **Autoencoder-based anomaly detection**

   * Autoencoders are trained primarily on benign system activity.
   * Reconstruction error is used as an anomaly score.
   * Higher reconstruction errors indicate behavior that differs from the learned benign patterns.

An explainability pipeline is also used to help investigate which log information contributes to the detected anomaly.

## Dataset

The experiments use the **DARPA Transparent Computing Engagement 3 (TC E3) APT dataset**.

The evaluation covers multiple performers and system contexts, including:

* 5dir
* cadets
* clearscope
* theia
* trace

The experiments consider several log contexts, including:

* ProcessAll
* Event
* Exec
* Parent
* Netflow

The dataset is processed into standardized log representations before generating embeddings.

## Experimental Setup

The main experimental pipeline evaluates combinations of:

* **17 embedding models**
* **11 autoencoder architectures**
* **5 log contexts**
* **5 performers**

This results in **4,400 experimental configurations**.

The anomaly detection setup uses:

* 80% benign data for training
* 20% data for testing
* Benign-only training
* Benign and anomalous samples during testing
* Standardized `Object_ID` representations

Due to the highly imbalanced nature of APT detection datasets, evaluation focuses primarily on anomaly-detection metrics rather than simple classification accuracy.

## Evaluation

The primary evaluation metrics include:

* AUC-ROC
* Reconstruction error
* Anomaly score distributions

The experimental results achieved an AUC-ROC of up to **0.9997** for the best-performing configuration.

## Explainable AI

The project includes an explainability component designed to provide insight into detected anomalies.

The objective is not only to determine whether a system log sequence is anomalous, but also to investigate the information contributing to the anomaly score.

The XAI pipeline is intended to support security analysts in understanding and investigating potentially malicious system behavior.

## Project Structure

The repository is organized around the experimental pipeline, notebooks, supporting resources, and results.

```text
XAI-APT-LLMs/
│
├── README.md
│
├── notebooks/
│   └── journal-llm-based-v1.ipynb
│
├── re/
│   └── ...
│
├── results/
│   └── ...
│
└── ...
```

The exact structure may change as the project is cleaned and prepared for reproducibility.

## Reproducibility

The experiments were developed using Python and Jupyter notebooks.

Before running the notebooks, install the required Python dependencies and ensure that the required dataset and embedding models are available.

A requirements file will be added as the project environment is finalized.

## Research Context

This repository supports research on:

* Advanced Persistent Threat detection
* Cybersecurity anomaly detection
* Large Language Models
* LLM embeddings
* Autoencoder architectures
* Explainable Artificial Intelligence
* System log analysis

## Publications

This project has contributed to the following research publications:

### 1. Semantic-Aware Advanced Persistent Threat Detection Using Autoencoders on LLM-Encoded System Logs

**Authors:** Waleed Khan Mohammed, Zahirul Arief Irfan Bin Shahrul Anuar, Mousa Sufian Mousa Mitani, Hezerul Abdul Karim, Nouar AlDahoul

**Year:** 2026

**arXiv:** [arXiv:2602.00204](https://arxiv.org/abs/2602.00204)

**BibTeX:**

```bibtex
@misc{mohammed2026semanticawareadvancedpersistentthreat,
  title={Semantic-Aware Advanced Persistent Threat Detection Using Autoencoders on LLM-Encoded System Logs},
  author={Waleed Khan Mohammed and Zahirul Arief Irfan Bin Shahrul Anuar and Mousa Sufian Mousa Mitani and Hezerul Abdul Karim and Nouar AlDahoul},
  year={2026},
  eprint={2602.00204},
  archivePrefix={arXiv},
  primaryClass={cs.CR},
  url={https://arxiv.org/abs/2602.00204}
}
```

### 2. XAI-APT: Explainable LLM-Based Advanced Persistent Threats Detection via Logs Embeddings and Autoencoders

**Authors:** Waleed Khan Mohammed, Hezerul Abdul Karim, Vik Tor Goh, Nouar AlDahoul

**Year:** 2026

**Published:** SSRN, June 4, 2026

**SSRN:** https://ssrn.com/abstract=6879858

**DOI:** [10.2139/ssrn.6879858](https://doi.org/10.2139/ssrn.6879858)

**Citation:**

```bibtex
@article{mohammed2026xai,
  title={XAI-APT: Explainable LLM-Based Advanced Persistent Threats Detection via Logs Embeddings and Autoencoders},
  author={Mohammed, Waleed Khan and Abdul Karim, Hezerul and Tor Goh, Vik and Aldahoul, Nouar},
  journal={Vik and Aldahoul, Nouar, XAI-APT: Explainable LLM-Based Advanced Persistent Threats Detection via Logs Embeddings and Autoencoders (June 04, 2026)},
  year={2026}
}
```

## Status

This repository contains research code and experimental materials. The implementation and documentation are being prepared for reproducibility and research dissemination.

## Author

**Mohammed Waleed Khan**
Bachelor of Engineering (Hons.) Electronics majoring in Computer

## License

A license will be added once the appropriate licensing terms for the research code and associated materials have been finalized.
