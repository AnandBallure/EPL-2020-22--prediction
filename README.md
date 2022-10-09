# EPL-2020-22--prediction
Predicting win/draw/loss for the seasons 2020-21 and 2021-22
 
 As it is a Multi-Class Classification, results above 50% Precision and F1 Score are fairly good.
 
 ## Collecting the Data
 - First, the data was collected from Kaggle using pandas. It had EPL match results from 1993 to 2022. 
 - The collected data is a csv file and encoded in latin-1  
 
 ## Cleaning the Data
 - As most of the teams have changed drastically since 1993, only the match results from the seasons 2020-21 and 2021-22 were used.
 - Created some new features from the existing ones. For example: There was data on Full_time_score and Total_shots_taken by each team for every match and thus, a new feature was created from that -- shot_accuracy, and so on.
 - Created the rolling averages for each team i.e., for evaluating the performance of teams over it's last three games.
 
 ## Preprocessing
 - Scaled the data with the help of Standard Scalar from Sklearn package.
 - Encoded the teams and referees, the data was now ready to split into training and testing.
 
 ## Splitting data 
 - As it is a prediction of the outcome of the football matches, data cannot be split randomly as it would be pointless to train a model over the future matches.
 - Target variable had 3 classes -> A, H, D {A: Away Team win, H: Home Team win, D: Draw}
 - Used pandas mapping function to map these to {H: 0, D:1, A:2}. The data is ready to be used for trained.
 
 ## Model Selection
 - Logistic Regressor, SVM and XGBoost models were used.
 
 ## Model Results
 - Logistic Regressor results:
 F1_score  : 0.66/W | 0.32/D | 0.74/L
 Precision : 0.74/W | 0.37/D | 0.64/L
 
 ![] (
 - XGBoost outperforms among the three with a F1_score of 0.75/W, 0.36/D, 0.74/L and a Precision of 0.75/W, 0.48/D, 0.61/L.
 - Clearly, the model has a hard time figuring out the correlations for the outcome "Draw".

 - 
