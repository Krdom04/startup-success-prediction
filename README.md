# startup-success-prediction
Predicting startup success based on around 1000 examples from the US<br/>
The database was taken from [Kaggle](https://www.kaggle.com/datasets/manishkc06/startup-success-prediction)
## Introduction
Startups are known to be one of the riskiest ventures one can take from virtually any perspective. Approximately 90% of startups fail in the long run according to the US Bureau of Labor Statistics <br/>
In this code, I analyze startups from many perspectives, predict startup success and it's most important indicators, and compare whether decision trees or logistic regression yield a more accurate result in predicting it.
## Results
As a simple layperson, my first assumption was the following: startups' success is mainly predicted by their: investor type (VC, angel), location, and category (enterprise, biotech etc.). So I firstly created a logistic regression model which only takes into account these features. The results were a mild 60.54% accuracy. <br/><br/>
Then I analyzed how big of a difference would it make if I took every numerical feature into account (obviously using label encoding string values). Using logistic regression again, I could increase the accuracy by almost 13%, which means a approximate of 75% accuracy, which is not considered bad. The highest accuracy I found on Kaggle for this database was 82%. <br/><br/>
Then I made a Decision Tree model, based on exactly the same data. Using entropy as criterion (meaning that the decision tree will try to keep entropy, aka. group seperation as big as possible) and a max depth of 4 (how complex it is), it could even further increase the accuracy by 5.16%.
![Source gv](https://github.com/Krdom04/startup-success-prediction/assets/161770019/836b1bfe-1abe-4ddc-8e44-201a36426eb0)<br/><br/>
The next interesting analysis was finding out which features have the most influence in startup prediction. This was done by sorting them by their coefficients (aka. log-odds per unit of change in input - for example if the feature is funding in total USD, then the coefficient tells us how much the log-odds increase if we add +1$ to the total funding). It turns out that the most important indicator, unsurprisingly is the funding in total USD, followed by the city of the startup. 
Finally, I plotted some interesting data, such as how the distribution of startups look like based on city, and comparing it with how it looks like for successful startups for example.
