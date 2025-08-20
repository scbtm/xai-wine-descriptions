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
The model is fine-tuned on a comprehensive wine review dataset from [Kaggle](https://www.kaggle.com/datasets/zynicide/wine-reviews), with reviews preprocessed to include structured information about country of origin and wine variety.

## Examples
<img width="1446" height="499" alt="example2" src="https://github.com/user-attachments/assets/2bc39609-28f8-461b-8258-6f53c464cb20" />
<img width="1434" height="492" alt="example1" src="https://github.com/user-attachments/assets/ab2bb865-f6e5-4ef6-9f46-7c12d0ec6e7a" />
<img width="1439" height="496" alt="example3" src="https://github.com/user-attachments/assets/48693f7a-8578-4302-a7e6-423cd7c5f105" />

    
