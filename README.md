# BAN5753_Spark_Team_10
Data and Reports for Mini Project 2

Executive Summary

Business Problem

  XYZ Bank wants to determine which customers from its direct marketing campaign are likely to subscribe to a term deposit. They have asked our group to analyze their marketing data and build a forecast model that will predict whether a customer subscribes or not. 
  
Data

   For this analysis, we utilized the given csv “XYZ_Bank_Deposit_Data_Classification”. This dataset consisted of 20 entries, or columns, and 41,188 rows. The data was pulled from the bank's direct marketing campaign where customers could have been reached through multiple forms of contact.
 
Data Cleaning

   In preparation for our model, we cleaned our data using four separate methods. First, we opted to handle the “999” variable in the “Pdays” column by generating a column that indicated pdays containing the “999” variable. Once the column was created, we then converted the variables containing the “999” to the column mean. Our next form of data cleaning consisted of dropping two columns, “nr.employed” and “emp.var.rate'”, to avoid multicollinearity. We then normalized the “duration” column, due to its wide range, using a standard scaler. Lastly, we utilized one-hot encoding on all string variables to allow our model to learn the relationships between different entries. 
 
Model Preparation and Building
