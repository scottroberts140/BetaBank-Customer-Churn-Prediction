# BetaBank Customer Churn Prediction

## Project Overview

This project predicts whether a customer will leave Beta Bank soon. Using feature engineering, data preparation, and machine learning model evaluation, the analysis identifies the optimal model configuration to achieve high predictive accuracy while maintaining operational compliance.

## Methodology

The project follows a systematic approach:

1. **Data Preparation**: Clean and prepare customer data for analysis
2. **Baseline Evaluation**: Train models using base features to establish performance baseline
3. **Feature Engineering**: Create interaction features to improve model performance
4. **Binning Analysis**: Apply age-based binning to capture non-linear relationships
5. **Model Selection**: Identify the champion model based on F1 score and AUC-ROC
6. **Final Testing**: Validate the champion model on held-out test data

## Key Features

- **Three DSR Libraries Integration**:
  - `dsr-data-tools`: Automated data analysis and recommendation generation
  - `dsr-feature-eng-ml`: Streamlined model evaluation and feature engineering
  - `dsr-utils`: Utility functions for data processing

- **Advanced Model Evaluation**:
  - Multiple model types: Decision Trees, Random Forests, Logistic Regression
  - Imbalance handling: Class weights, auto-balancing, SMOTE
  - Hyperparameter optimization: GridSearchCV and RandomizedSearchCV

- **Interaction Features**:
  - Balance vs. EstimatedSalary
  - CreditScore vs. Age
  - Balance vs. Active Member status
  - Tenure per Age
  - Products Active (number of products × active status)

## Results

**Champion Model**: Random Forest with Auto-Balancing

- **Validation F1 Score**: 0.6150
- **Test F1 Score**: 0.5983
- **Test AUC-ROC**: 0.8481

The high AUC-ROC score validates the fundamental quality of the model, while the F1 score demonstrates operational success and compliance with the project's 0.59 minimum threshold.

## Project Structure

```
BetaBank/
├── BetaBank.ipynb          # Main analysis notebook
├── datasets/
│   ├── Churn.csv           # Customer churn data (CSV format)
│   ├── Churn.xlsx          # Customer churn data (Excel format)
│   ├── users_behavior.csv  # Behavioral data (CSV format)
│   └── users_behavior.xlsx # Behavioral data (Excel format)
└── README.md
```

## Technical Stack

- **Python**: 3.13.7
- **Data Processing**: pandas 2.x
- **Machine Learning**: scikit-learn
- **Scientific Computing**: scipy, numpy
- **Visualization**: matplotlib, seaborn

## Installation

1. Clone the repository
2. Install required dependencies:
   ```bash
   pip install pandas scikit-learn scipy numpy matplotlib seaborn
   ```
3. Install DSR libraries (if available in your environment):
   ```bash
   pip install dsr-data-tools dsr-feature-eng-ml dsr-utils
   ```

## Usage

Open `BetaBank.ipynb` in Jupyter Notebook or JupyterLab:

```bash
jupyter notebook BetaBank.ipynb
```

Execute the cells sequentially to reproduce the analysis and results.

## Key Insights

1. **Feature Interactions Matter**: Adding interaction features improved the model's F1 score from 0.6046 to 0.6150
2. **Random Forests Excel**: Random Forest models consistently outperformed Decision Trees and Logistic Regression
3. **Auto-Balancing is Effective**: Automatic class balancing provided the best results without manual tuning
4. **Threshold Met**: The final model achieves an F1 score of 0.5983, exceeding the 0.59 project goal

## Author

Created as part of the TripleTen Data Science program, Sprint 9 - Feature Engineering

## License

This project is for educational purposes.
