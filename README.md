# machine_failure_prediction
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
              precision    recall  f1-score   support

           0       1.00      0.86      0.92      1932
           1       0.18      0.88      0.30        68

    accuracy                           0.86      2000
   macro avg       0.59      0.87      0.61      2000
weighted avg       0.97      0.86      0.90      2000

=== Decision Tree ===
              precision    recall  f1-score   support

           0       0.99      0.99      0.99      1932
           1       0.76      0.76      0.76        68

    accuracy                           0.98      2000
   macro avg       0.88      0.88      0.88      2000
weighted avg       0.98      0.98      0.98      2000

=== Random Forest ===
              precision    recall  f1-score   support

           0       0.99      1.00      1.00      1932
           1       0.95      0.82      0.88        68

    accuracy                           0.99      2000
   macro avg       0.97      0.91      0.94      2000
weighted avg       0.99      0.99      0.99      2000

## Results
Random Forest was selected as the final model. The decision threshold was adjusted from 0.50 to 0.38 using the Precision-Recall curve, increasing recall from 0.76 to 0.82 while maintaining precision at 0.95
Out of 68 real failures in the test set, the model detected 56. Of the 59 alerts generated only 3 were false alarms. This balance was chosen deliberately to avoid alarm fatigue in the maintenance team because a low precision system risks being ignored over time, reducing the value of the system.

## Author
Jorge - Mechatronics Engineer with experience in industrial maintenance.
[LinkedIn](www.linkedin.com/in/jorgenavao)


