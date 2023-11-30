# BAN5753_Spark_Team_10
Data and Reports for Mini Project 2

Executive Summary

Business Problem
 	
  XYZ Bank wants to determine which customers from its direct marketing campaign are likely to subscribe to a term deposit. They have asked our group to analyze their marketing data and build a forecast model that will predict whether a customer subscribes or not. 


Data
  	
  For this analysis, we utilized the given csv “XYZ_Bank_Deposit_Data_Classification”. This dataset consisted of 20 entries, or columns, and 41,188 rows. The data was pulled from the bank's direct marketing campaign where customers could have been reached through multiple forms of contact.


Data Cleaning

  In preparation for our model, we cleaned our data using four separate methods. First, we opted to handle the “999” variable in the “Pdays” column by generating a column that indicated pdays containing the “999” variable. Once the column was created, we then converted the variables containing the “999” to the column mean. Our next form of data cleaning consisted of dropping two columns, “nr.employed” and “emp.var.rate'”, to avoid multicollinearity. We then normalized the “duration” column, due to its wide range, using a standard scaler. Lastly, we utilized one-hot encoding on all string variables to allow our model to learn the relationships between different entries.


Model Preparation
	
  After cleaning our data, we helped prepare our model further by creating bins for the age and duration columns to group variables into more manageable variables and reduce overfitting our model. We then split the data into a training and test set with a split of 70/30 respectfully. The model was then trained using logistic regression and predictions were made on the test set. After checking for accuracy, our model predicted the test set with 90.45% accuracy. 


Model Building
	
  For our model, we decided to utilize a random forest model due to its ability to interpret feature importance for our prescriptive analytics as well as its ability to handle categorical data. In addition to those benefits, random forest also can test for uncertainty in our predictions that can test the reliability of our model for XYZ Bank. To run our model, we applied the vector assembler and then split the data, once again, into a training and test set with a 70/30 split. After running our final model through the training set we had an accuracy score of 89.75%. 

Model Outcome

   With our final model running an acceptable accuracy score of 89.75%, we turned to the prescriptive portion of our analysis by running code for feature importance. This helped us determine some of the key features our random forest utilized to make its predictions. Based on the outcome of that code, our model identified the “duration_group_index”, “euribor3m”, and “pdays_missing” entries as the three most important features. In order to determine how those features factored into these models’ decision we ran further code that grouped the “y_index” by its outcome and then aggregated for the mean output of each of those features. With the mean of both groups in the “pday_missing” entry being close to 1, it is safe to assume that while the feature may have been important in our model’s selection, a majority of the customers in the analysis had been contacted previously.
 
Recommendations

   Based on the results of our model, feature analysis, and breakdown of the top three features we were now able to make a recommendation to XYZ Bank to help identify and improve their enrollment. Given the average duration group index of 0.09 we can determine that the majority of the calls our model predicted to be positive enrollment were under 500 seconds and primarily in our “0” group. We can also conclude, based on the average, that the majority of positive enrollment predictions had an average Euribor 3-month rate of 2.12%. Therefore, our recommendations to XYZ Bank, based on our models’ predictions, would be to focus their next campaign towards previously contacted customers, to keep their contact durations under 500 seconds, approximately 8 minutes, and to focus on starting the campaign when rates are closer to 2.12% or lower. By doing so, they should be able to target customers who are more susceptible to enrolling.
