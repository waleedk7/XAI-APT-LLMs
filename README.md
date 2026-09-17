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

* **16 embedding models**
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

## Related Work

**XAI-APT: Explainable LLM-Based Advanced Persistent Threats Detection via Logs Embeddings and Autoencoders**

The research investigates the combination of LLM-based semantic log embeddings, autoencoder anomaly detection, and explainability for APT detection.

## Status

This repository contains research code and experimental materials. The implementation and documentation are being prepared for reproducibility and research dissemination.

## Author

**Mohammed Waleed Khan**

Bachelor of Engineering (Hons.) Electronics Engineering, majoring in Computer Engineering

## License

A license will be added once the appropriate licensing terms for the research code and associated materials have been finalized.
