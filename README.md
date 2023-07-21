# RUL-prediction-of-offshore-wind-turbine
source codes for my journal

Codes are divided into two main parts: LightGBM model and GRU-BNN. 

The file "lightGBM model" only utilizes dfT01combined.csv. After running all the codes in this file, you will get resLGBMT.csv which is the residuls of temperatures. 
Since there still exists some randomness in LightGBM model, one sample of resLGBMT.csv for my journal is uploaded. 
This file conducts the following procedure for 9 temperatures: 1.grid search  2.feature rank and selection 3. the second grid search 
The table of results will be created in the final part of saving and analysis. 

The second file "GRU-BNN" uses resLGBMT.csv as input. It compares different baseline models including SVR, Elastic net, GRU, LSTM, CNN, RNN etc by 5-fold validation. 
The predictions and its average from GRU are fed into BNN to get the final prediciton and confidence interval. For convinence, some parts include codes on test sample 
in each machine learning methods. It depends on you are willing to see these results or not. If not, cross validation is enough to show the performance of models. The simplest 
way to reproduce my results is to jump other machine learning methods, directly run GRU and BNN. 

For BNN, I use 5000 experiments to get the final result and confidence interval. This nerual network uses the sum of KL loss, RMSE and MAE as loss to make itself converge, while 
other machine methods uses RMSE and MAE. Therefore, it should be careful to keep metrics same when comparing results from different models.

dfb.csv is a sample for RUL prediction from GRU. 

