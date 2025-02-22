# Audio Classification with AST Model

This repository contains scripts for training and evaluating an Audio Spectrogram Transformer (AST) model on an audio classification task. The project focuses on handling class imbalance through label merging, data augmentation, and class-weighted loss functions.

- [Audio Classification with AST Model](#audio-classification-with-ast-model)
  - [Project Overview](#project-overview)
  - [Files Description](#files-description)
    - [1. `0_data_exploration.py`](#1-0_data_explorationpy)
    - [2. `1_AST_class_weights.py`](#2-1_ast_class_weightspy)
    - [3. `2_Labels_data_aug.py`](#3-2_labels_data_augpy)
    - [4. `3_AST_class_weights_reduce_DataLabels.py`](#4-3_ast_class_weights_reduce_datalabelspy)

## Project Overview

- **Objective**: Classify audio clips into emotion-based categories (e.g., "Celebration", "Disappointment").
- **Challenges**: 
  - Class imbalance in the dataset.
  - Difficulty distinguishing between similar labels (e.g., "Excitement" vs. "Celebration").
- **Solutions**:
  - Class-weighted loss to address imbalance.
  - Data augmentation for underrepresented classes.
  - Merging similar labels to reduce complexity.

---

## Files Description

### 1. `0_data_exploration.py`
- **Purpose**: Exploratory data analysis (EDA) for audio dataset.
- **Key Features**:
  - Visualizes waveforms, spectrograms, and frequency spectra.
  - Analyzes label distribution.
  - Plays audio samples for each class.

### 2. `1_AST_class_weights.py`
- **Purpose**: Baseline training script for the AST model with class-weighted loss.
- **Key Features**:
  - Uses `MIT/ast-finetuned-audioset` pre-trained model.
  - Applies class weights to handle imbalanced data.
  - Includes training logs, loss curves, and evaluation metrics.

### 3. `2_Labels_data_aug.py`
- **Purpose**: Augment specific labels ("Excitement" and "Disappointment") to improve differentiation.
- **Key Features**:
  - Applies noise, pitch shifting, and time stretching.
  - Trains model on augmented data and evaluates confusion matrices.

### 4. `3_AST_class_weights_reduce_DataLabels.py`
- **Purpose**: Explore label merging and data augmentation to improve metrics.
- **Key Features**:
  - Merges labels like "Celebration" & "Excitement" to reduce model complexity.
  - Augments "Disappointment" with noise, pitch shifting, and time stretching.
  - Trains model on augmented and merged data
