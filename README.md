# 🍷 Wine Review Quality Classification with Explainable AI

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Transformers](https://img.shields.io/badge/🤗%20Transformers-4.0+-orange.svg)](https://huggingface.co/transformers/)
[![Gradio](https://img.shields.io/badge/Gradio-Interface-green.svg)](https://gradio.app/)
<!-- [![License](https://img.shields.io/badge/License-MIT-red.svg)](LICENSE) -->

## 🎯 Project Overview

This project presents an explainable AI approach for classifying wine reviews using **ModernBERT**, a recent transformer architecture. The system predicts wine quality and provides **human-interpretable explanations** for its decisions, making it useful for sommeliers, wine enthusiasts, and businesses.

### 🚀 Technical Details
- **70.2% accuracy** on 169K+ wine reviews with 4-class classification
- **ModernBERT fine-tuning** with standard optimization techniques
- **Explainable AI** with Integrated Gradients
- **Interactive web interface** for real-time predictions and explanations
- **Model tracking pipeline** with TensorBoard and [huggingface](https://huggingface.co/scbtm/ModernBERT_wine_quality_reviews_ft)

## ✨ Advanced Features

### 🔬 Explainable AI Implementation
- **Integrated Gradients**: Attribution method showing which words influence predictions
- **Subword Token Merging**: Algorithm for improved readability of explanations
- **Real-time Visualization**: Interactive word importance highlighting with confidence scores
- **Attribution Score Analysis**: Quantitative measures of feature importance

### 🎨 Interactive Interface
- **Gradio Web App**: UI for model interaction
- **Live Predictions**: Instant wine quality assessment with confidence intervals
- **Visual Explanations**: Color-coded word importance visualization
- **Example Gallery**: Examples showcasing model capabilities

### 🏗️ Technical Architecture
- **ModernBERT Base**: Cutting-edge transformer architecture optimized for efficiency
- **Training**: Early stopping, warm-up scheduling, gradient clipping

## 🔧 Model Training & Optimization

The model uses a wine review dataset from [Kaggle](https://www.kaggle.com/datasets/zynicide/wine-reviews) with the following preprocessing steps:

- **169K+ wine reviews** across 4 quality categories
- **Structured input format**: "Country: [X]; Variety: [Y]; Description: [Z]"
- **Binning strategy**: Points-based quality categorization (≤85: bad, 86-88: average, 89-92: good, >92: excellent)
- **Training techniques**: Learning rate scheduling, gradient norm clipping, early stopping

## 🏆 Performance Metrics

| Metric | Score | Details |
|--------|--------|---------|
| **Accuracy** | 70.2% | 4-class wine quality classification |
| **F1-Score** | 70.2% | Weighted average across all classes |
| **Dataset Size** | 169K+ | Comprehensive wine review corpus |
| **Training Time** | ~4.8K steps | Optimized with early stopping |

## 📊 Live Demonstrations

### Explainable AI Predictions
The system provides wine quality predictions with visual explanations showing which words most influence the decision:

<img width="1446" height="499" alt="example2" src="https://github.com/user-attachments/assets/2bc39609-28f8-461b-8258-6f53c464cb20" />

*Example: Excellent wine prediction with attribution highlighting key quality indicators*

<img width="1434" height="492" alt="example1" src="https://github.com/user-attachments/assets/ab2bb865-f6e5-4ef6-9f46-7c12d0ec6e7a" />

*Example: Average wine classification showing balanced attribution across descriptors*

<img width="1439" height="496" alt="example3" src="https://github.com/user-attachments/assets/48693f7a-8578-4302-a7e6-423cd7c5f105" />

*Example: Good wine prediction with clear positive sentiment attribution*

## 🛠️ Technical Implementation

### Core Technologies
- **🤗 Transformers**: ModernBERT implementation with custom fine-tuning
- **PyTorch**: Deep learning framework with CUDA support
- **Captum**: Library for Integrated Gradients
- **Gradio**: Interactive web interface framework
- **Scikit-learn**: Metrics evaluation and data splitting
- **Pandas/NumPy**: Data manipulation and numerical computing


### Explainability Pipeline
1. **Input Processing**: Tokenization with ModernBERT tokenizer
2. **Attribution Computation**: Integrated Gradients with 50 steps
3. **Subword Merging**: Algorithm for readable explanations
4. **Visualization**: HTML-based color-coded word importance

## 🔍 Understanding Integrated Gradients

**What is Integrated Gradients?**
Integrated Gradients is a method that explains AI model predictions by measuring how much each input word contributes to the final decision. It helps to answer: *"If I gradually add each word to an empty sentence, how much does each word change the model's prediction?"*

**How It Works (Simple Explanation)**
1. **Start with a baseline**: Begin with a "neutral" input (like a sentence of padding tokens)
2. **Create a path**: Draw a straight line from this baseline to your actual wine review
3. **Take small steps**: Move along this path in tiny increments (we use 50 steps)
4. **Measure changes**: At each step, see how much the prediction changes
5. **Sum the contributions**: Add up all the changes to get each word's importance score

*This is an intuitive explanation. In reality, Integrated Gradients (IG) doesn’t reveal words sequentially. It scales the whole input continuously from the baseline to the real input in many small steps in embedding space. Think “turning the volume knob from 0% to 100%,” not “adding words gradually.”*

**Visual Example**
```
Baseline:    [PAD] [PAD] [PAD] [PAD] [PAD]     → Prediction: 25% "good"
Step 1:      "This" [PAD] [PAD] [PAD] [PAD]   → Prediction: 28% "good" (+3%)
Step 2:      "This wine" [PAD] [PAD] [PAD]    → Prediction: 35% "good" (+7%)
Step 3:      "This wine is" [PAD] [PAD]       → Prediction: 40% "good" (+5%)
...
Final:       "This wine is absolutely amazing" → Prediction: 95% "good"
```

**Why This Matters**
- **Reliable**: Integrated Gradients satisfies mathematical properties that make explanations more robust, such as completeness (the attributions across tokens sum approximately to the model’s output difference between input and baseline).
- **Intuitive**: The results often match human intuition about which words seem important
- **Comprehensive**: Every word gets a score, showing both positive and negative contributions

**In This Wine Classifier**
When you see words highlighted in blue (positive) or red (negative), those colors represent how much each word pushed the prediction toward or away from the final quality rating. Stronger colors mean bigger influence.

## 🎯 Business Applications

- **Wine Industry**: Quality assessment support for wineries and distributors
- **E-commerce**: Automated product categorization and recommendation systems
- **Market Research**: Consumer preference analysis and trend identification