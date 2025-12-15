# SHL AI Intern Hiring – Nov 2025 Assessment Submission  
## Grammar Scoring Engine from Voice Samples

## Overview
This project implements an end-to-end **Grammar Scoring Engine** that predicts grammatical proficiency scores from spoken audio responses. The solution is designed to be **interpretable, lightweight, and scalable**, aligning with real-world assessment system requirements.

---

## Problem Statement
Given short audio recordings of spoken responses, the goal is to automatically predict a **continuous grammar score** that reflects grammatical correctness and fluency.

---

## Approach

The solution decomposes the problem into modular stages:

### 1. Speech-to-Text (ASR)
- Audio responses are transcribed using **OpenAI Whisper (tiny model)**.
- A lightweight ASR model is chosen to balance accuracy and computational efficiency.

### 2. Feature Extraction

#### Acoustic Features
- MFCC-based representations extracted from audio
- Statistical descriptors applied:
  - Mean
  - Standard deviation
  - Minimum
  - Maximum  
- These capture pronunciation consistency, articulation, and acoustic variability.

#### Linguistic & Fluency Features
- Number of words
- Average word length
- Sentence count
- Lexical diversity
- **Speech rate (words per second)** as a fluency proxy

These features are commonly correlated with grammar quality in spoken language assessment.

### 3. Modeling
- A **regression-based approach** using XGBoost
- Predicts continuous grammar scores
- Chosen for robustness, interpretability, and strong performance on tabular features

---

## Dataset
The dataset is provided as part of the **SHL Intern Hiring Assessment (2025)** and consists of:
- Audio recordings (`.wav`)
- Corresponding grammar scores for training
- Unlabeled test audio samples for evaluation

---

## Evaluation
- The model is trained on labeled audio samples
- Predictions are generated for unseen test data
- Performance is optimized for correlation-based evaluation metrics used in the competition

---

## Results
- The final predictions are stored in `submission.csv`
- The approach prioritizes **generalization and explainability** over leaderboard-specific overfitting

---

## Limitations & Future Work
- Incorporating pause duration and silence-based fluency features could further improve performance
- End-to-end pretrained speech models (e.g., wav2vec2) can be explored for higher accuracy
- Grammar-specific error detection can be added in less constrained environments

---

## How to Run
1. Install dependencies from `requirements.txt`
2. Open and run `shl_grammar_scoring_engine.ipynb`
3. The final output file `submission.csv` will be generated

---

## Repository Structure
