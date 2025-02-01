# Wine Review Quality Classification with XAI

## Overview
This project implements an explainable AI system for classifying wine reviews using ModernBERT. The system analyzes wine reviews and classifies them into four quality categories while providing interpretable explanations for its predictions.

## Features
- Wine review quality classification (bad, average, good, excellent)
- Integrated Gradients for model interpretability
- Interactive Gradio interface for real-time predictions
- Visualization of word importance in predictions
- Support for structured wine review inputs (country, variety, description)

## Explainability Features
- Word importance highlighting using Integrated Gradients
- Attribution score visualization
- Subword token merging for improved readability

## Model Training
The model is fine-tuned on a comprehensive wine review dataset from Kaggle, with reviews preprocessed to include structured information about country of origin and wine variety.
    