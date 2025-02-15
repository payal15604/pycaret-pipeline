# Binary Classification with PyCaret  

## Overview  
This repository contains a **fully automated** binary classification pipeline using **PyCaret**. No manual feature engineering, no complex model selection—just load your dataset and let PyCaret do the heavy lifting.  

## Features  
- **Automated Model Selection** – Compares multiple models and selects the best one.  
- **Minimal Code, Maximum Performance** – Train, evaluate, and deploy models in a few lines.  
- **Built-in Visualizations** – Get confusion matrices, AUC curves, and feature importance instantly.  
- **Seamless Model Deployment** – Save and reload trained pipelines effortlessly.  

## Usage  

1. **Load Dataset**  
from pycaret.datasets import get_data data = get_data('diabetes')


- Loads a sample dataset. Replace 'diabetes' with your own dataset or use a custom CSV.

2. **Initialize PyCaret**  
from pycaret.classification import * s = setup(data, target='Class variable', session_id=123)


- `setup()`: Initializes the PyCaret environment.
- `target`: Specifies the column to predict.
- `session_id`: Ensures reproducibility.

3. **Compare Models & Select the Best**
   best_model = compare_models()


- `compare_models()`: Runs multiple classifiers and picks the best-performing one.

4. **Alternative: Object-Oriented Approach**  
from pycaret.classification import ClassificationExperiment exp = ClassificationExperiment() exp.setup(data, target='Class variable', session_id=123) best_model = exp.compare_models()


- Uses an OOP-based workflow, giving more flexibility for experimentation.

5. **Visualize Results**  
plot_model(best_model, plot='confusion_matrix') plot_model(best_model, plot='auc') plot_model(best_model, plot='feature')


- `plot_model()`: Generates built-in visualizations.
  - `confusion_matrix`: Shows model accuracy.
  - `auc`: Displays the ROC curve.
  - `feature`: Highlights important features.

6. **Make Predictions**  
predictions = predict_model(best_model, data=new_data)


- `predict_model()`: Runs predictions on new data.

7. **Save & Load the Trained Pipeline**  
save_model(best_model, 'binary_classification_pipeline') loaded_model = load_model('binary_classification_pipeline')


- `save_model()`: Saves the trained pipeline for reuse.
- `load_model()`: Loads the saved pipeline.

## What's Next  
- Custom dataset support  
- Hyperparameter tuning  
- More advanced visualizations  

## License  
MIT License – Free to use and modify.
