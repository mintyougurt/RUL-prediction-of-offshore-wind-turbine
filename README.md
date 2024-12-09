# RUL-prediction-of-offshore-wind-turbine
for my journal: Gearbox pump failure prognostics in offshore wind turbine by an integrated data-driven model 
please check https://doi.org/10.1016/j.apenergy.2024.124829

# Abstract:
This journal presents two-stage models for Remaining Useful Life (RUL) prediction of offshore wind turbines. The first model utilizes the LightGBM algorithm for temperature prediction, while the second model employs a GRU-BNN (Bayesian Neural Network) approach for RUL prediction based on residuals from LightGBM. The models are evaluated on a dataset, and the results are compared against various baseline machine learning models to demonstrate their effectiveness. The proposed GRU-BNN model combines the predictions from GRU with Bayesian Neural Networks (BNN) to provide a final prediction along with confidence intervals. The entire workflow is implemented in Python and is recommended to be executed on Google Colab for optimal performance.

# 1. LightGBM Model:
The LightGBM model aims to predict 9 temperatures in offshore wind turbines using the dataset "dfT01combined.csv." The code is divided into three main steps:

Grid Search: Hyperparameter tuning is performed using grid search to find the optimal parameters for the LightGBM model.
Feature Rank and Selection: Feature importance analysis is conducted to identify the most relevant variables for temperature prediction.
Second Grid Search: Another grid search is carried out after feature selection to further optimize the model.

The final output of this part is "resLGBMT.csv," which contains the residuals of the temperature predictions. A sample of this file is provided for reference.

# 2. GRU-BNN Model:
The GRU-BNN model uses the "resLGBMT.csv" file as input for RUL prediction. The code compares different baseline machine learning models, including SVR, Elastic Net, GRU, LSTM, CNN, and RNN, through 5-fold cross-validation. The GRU model's predictions and their average are fed into the BNN to obtain the final RUL prediction along with confidence intervals.

The key steps involved in the GRU-BNN model are as follows:

Baseline Model Comparison: Several machine learning models are compared using 5-fold cross-validation. Optionally, predictions on test samples can also be obtained.
GRU Model: The Gated Recurrent Unit (GRU) model is implemented for RUL prediction.
BNN Implementation: Bayesian Neural Networks (BNN) are used to combine the predictions from the GRU model and derive a final prediction with confidence intervals. The BNN is trained with 5000 experiments, using the sum of KL loss, RMSE, and MAE as loss functions.

Results and Analysis:
The final results and comparison table for all models are saved and analyzed. The metrics used for evaluation, such as RMSE and MAE, are consistent across all models to ensure fair comparisons.

# Reproducing the Results:
To reproduce the results presented in this journal, follow these steps:

Run the LightGBM model code on the "dfT01combined.csv" dataset to obtain "resLGBMT.csv."
Optionally, skip the other machine learning methods and directly execute the GRU and BNN parts for RUL prediction and confidence intervals.

# Conclusion:
The presented RUL prediction models using LightGBM and GRU-BNN demonstrate promising performance for offshore wind turbines. The proposed GRU-BNN model offers accurate RUL predictions along with uncertainty quantification, making it a valuable tool for decision-making and maintenance planning in the renewable energy sector.

Keywords: Remaining Useful Life Prediction, Offshore Wind Turbine, LightGBM, GRU, BNN, Machine Learning, Confidence Intervals.

Note: The data used in this project have been cleaned extensively. To ensure proper usage and respect for the work involved, only the original data are available upon request. please check https://www.edp.com/en/innovation/open-data
