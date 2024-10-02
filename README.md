# Fashion E-commerce Product Success Prediction

## Problem Statement
A fashion e-commerce company is planning its collections for the upcoming year. The company has created many potential products as candidates and now wants to estimate which products would be successful (top) or not (flop). You are provided with historic data from the past two years and potential future products, and the task is to create a machine learning model to predict the success of these products.

## Data Overview
The data consists of two files:
- **Historic Data (historic.csv)**: Contains 8000 past products with labels indicating whether they were successful (`top`) or not (`flop`).
- **Prediction Data (prediction_input.csv)**: Contains 2000 future product candidates without labels, which are to be predicted by the model.

### Data Columns:
- `item_no`: Internal identifier for a past product or a product candidate for the future.
- `category`: Category of the product.
- `main_promotion`: Main promotion used to promote the product.
- `color`: The main color of the product.
- `stars`: Customer review ratings from 0 (negative) to 5 (positive).
- `success_indicator`: Indicator of whether a product was successful (top) or not (flop) in the past. Only present in the historic data.

## Project Structure
```bash
.
├── EDA.ipynb               # Notebook for Exploratory Data Analysis (EDA)
├── model_training.ipynb     # Notebook for model training and selection
├── model_prediction.ipynb   # Notebook for generating predictions
├── data/
│   ├── historic.csv         # Historic product data
│   └── prediction_input.csv # Prediction product data
└── README.md                # Project README file (this file)
```

## Solution Approach
1. **Exploratory Data Analysis (EDA)**: 
   - Performed EDA on `historic.csv` to analyze patterns and relationships in the data.
   - Checked for missing values, explored the distribution of features like `category`, `main_promotion`, `color`, and `stars`, and analyzed the correlation between the features and the target variable `success_indicator`.
   
   Notebook: [EDA.ipynb](EDA.ipynb)

2. **Model Training**:
   - Used PyCaret to train and evaluate multiple classification models.
   - Selected the best-performing model based on accuracy and other metrics.
   - Followed an object-oriented, class-based approach to design the model workflow.
   
   Notebook: [model_training.ipynb](model_training.ipynb)

3. **Model Prediction**:
   - Used the trained model to predict the success of potential future products in the `prediction_input.csv` file.
   - Added a `success_indicator` column to the predictions.
   
   Notebook: [model_prediction.ipynb](model_prediction.ipynb)

## Evaluation Metrics
The following metrics were considered during model selection:
- Accuracy
- Precision
- Recall
- F1-Score
- AUC-ROC Curve

## Model Selection
The best model was selected based on its performance during training and validation using the metrics mentioned above. PyCaret automatically handles model comparison and selects the best-performing model.

## How to Run the Code
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/fashion-product-prediction.git
   cd fashion-product-prediction
   ```

2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. Perform EDA:
   - Run the `eda.ipynb` notebook to visualize and analyze the data.

4. Train the model:
   - Run the `model_training.ipynb` notebook to train the classification models using PyCaret.

5. Generate Predictions:
   - Run the `model_prediction.ipynb` notebook to make predictions on the future product data (`prediction_input.csv`).

## Conclusion
This project demonstrates a machine learning workflow for predicting the success of fashion e-commerce products based on historic data. PyCaret simplifies the process of training and selecting the best classification model, while the object-oriented approach ensures a clean and modular code structure.
