# Module 14 Challenge

This module's challenge is to create an algorithmic trading strategy that uses machine learning to produce trading signals, thus automating the trading decisions, and then adjust the parameters to optimize the trading algorithm. 


### Establish a Baseline Performance

![image.](SVM_image.png)

Using the SVC classifier model from SKLearn's support vector machine (SVM) to fit the training data and make predictions based on the testing data for the baseline algorithm, we generated the following classification report:

![image.](SVM_report.png)

With 43% accuracy for the sell signal (-1.0) and 56% accuracy for the buy signal (1.0), we haven't created a very reliable model. But this is our baseline. We will use it to compare the effects of tuning the trading algorithm. This algorithm used a training window of 3 months.


## Tune the Baseline Trading Algorithm

We adjusted the DateOffset value from 3 months to 6 months and got slightly better results. By increasing the training window, our accuracy and returns improved.

![image.](6_month_revised.png)

The next adjustment we made was to change the short and long SMA windows from 4 and 100 to 2 and 50, respectively. This seems to have erased the improvements we made when we extended the DateOffset value from 3 to 6 months. The set of parameters that best improved the trading algorithm returns is shown above.

### Evaluate a New Machine Learning Classifier

A new classifier was imported from SKLearn, LogisticRegression. Using the original training data as the baseline model, we fit another model with the new classifier.

The new model was backtested and the following image shows the cumulative product of the actual returns vs the strategy returns. The precision improved slightly and the returns improved. In summary, this trading algorithm was a higher risk, higher return strategy.

![image.](LR_image.png)



### Conclusions

The best performing model was our baseline trading algorithm, tuned to a 6 month DateOffset value. 


