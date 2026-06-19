# Machine_Failure_prediction
Machine learning project focused on predictive maintenance using operational data from an industrial enviroment. The goal is to predict wether a machine will fail based on sensor readings, suppporting maintenance teams in prioritizing interventions before failures occurs.

## Dataset  
AI4I 2020 Predictive Maintenance Dataset -- UCI Machine Learning Repository 10,000 observations with 6 features.  

Features used:
- Air temperature [K]
- Process temperature [K]
- Rotational speed [rpm]
- Torque [Nm]
- Tool wear [min]
- Type (L,M,H)

Engineered features:
- Temp_diff (Air - Process)
- Power (Torque × RPM)
- Overstrain (Torque × Tool wear)

## Models trained
=== Logistic Regression ===

              precision    recall    support
           0       1.00      0.86       1932
           1       0.18      0.88         68

=== Decision Tree ===

              precision    recall    support
           0       0.99      0.99       1932
           1       0.76      0.76         68


=== Random Forest ===

              precision    recall   support
           0       0.99      1.00      1932
           1       0.95      0.82        68

## Results
Random Forest was selected as the final model. The decision threshold was adjusted from 0.50 to 0.38 using the Precision-Recall curve, increasing recall from 0.76 to 0.82 while maintaining precision at 0.95.
Out of 68 real failures in the test set, the model detected 56. Of the 59 alerts generated only 3 were false alarms. This balance was chosen deliberately to avoid alarm fatigue in the maintenance team because a low precision system risks being ignored over time, reducing the value of the system.

## Author
Jorge - Mechatronics Engineer with experience in industrial maintenance.
[LinkedIn](https://www.linkedin.com/in/jorgenavao)


