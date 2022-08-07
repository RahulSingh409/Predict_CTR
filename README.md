# Predict_CTR
Predict_CTR

What kind of problem are we trying to solve?
* The problem that we are given is to predict CTR (Click Through Rate) of an email campaign. This help the organization to see is there users are responding or not. It act as a relationship between them. So, the business objective is how to increase the CTR and predict the CTR.
* The dtypes for our variables are numerical and categorical. Some of the dtypes provide are not in Boolean for them we have to convert them to bolean structure.
* We have first checked the statistical details of the variable and we got to know that many of the variables averageare near to zero. The variables contain to much of outliers as the max and median has quite distance in it. 
* For feature engineering we have drop of the campaign_id as they are not important to us. We have also drop the is_timer column as the value consists in it zero both train and test data. We have encoded times_of_day and saved in times_of_day_ID. As that will help model to predict on the basis of categorical. ‘is_price’ column given to us was not in Boolean so we converted it Boolean. 
* While seeing the correlation of target variables with others there is no high correlation we got. That means target variable have week linearity with others.
* Strong correlation is there between no_of_CTA and body_len, subject_len is moderately correlated with body_len and no_of_CTA.
* mean_paragraph_len is highly negative correlated with body_len.
* We have explore the feature on the distplot and box plot and got that the variables are not normally distributed and they have to much of outliers.
* So, our task is to make the distribution normal so that the outliers can also come near to the mean. As there are a lot of outliers and we cannot remove them nor we can adjust them as the dataset is also to small, doing so will drastically change our prediction. 

* With the regplot we came to know that only mean_paragraph_len' & 'product' are giving linear relation as it increases with the target variables. Many of the variables are negatively related to target variables. So it will be difficult for us to predict.
* Through Bar plot feature exploration on different variables compared with target variables. Most of the variables are averagely good for CTR. The bar plot helped us to know how to use each and every variable to get more CTR.
* As our dataset is having to many outliers so we have produced a skewness table to know how each of the variables is highly skewed.
* VIF help us in detecting multicollinearity. But we are not trying to remove the feature as our evaluation matrix is R2 and in r2 if there are more and more features it will help us in good scoring. Also many of the machine learning algorithms don’t get affected by multicollinearity.
* We have also produced the WOE. WoE helps check the linear relationship of a feature with its dependent feature to be used in the model. IV is a good measure of the predictive power of a feature and it also helps point out the suspicious feature. Some of our variable IV value is too low, we will remove them if our model don’t predict the good accuracy value. But now we will keep it and we will solve this with Cross Validation techniques.
* We have used multiple models for predicting the regression. We have also used different hyperparameter techniques. Hyperparameters maximize the model's performance, minimizing a predefined loss function to produce better results with fewer errors. We have used different hyperparameter values as they cannot be defined which is best or better so we have changed it a lot of times to get a better result. 
* In our first Model1 we don’t get a good evaluation value of r2. although we have just used simple techtics.
* Under cross validation Model2 everything has changed, we have used kfold for the model validation technique. Cross-validation is a resampling procedure used to evaluate machine learning models on a limited data sample. The procedure has a single parameter called k that refers to the number of groups that a given data sample is to be split into.          
* On cross-validation we got to know that which of our model is giving us best result so that we can use it for further processing. 
* Next after getting to know each model we used Stacking techniques Stacking enables us to train multiple models to solve similar problems, and based on their combined output, it builds a new model with improved performance. Well, the ultimate goal of stacking is a smaller risk of overfitting. It helps us to characterize the different models. It help us to make a weak model strong and a strong one more predictable.
* Lastly, why I have used the blending technique? Well, Blending is an ensemble machine learning technique that uses a machine learning model to learn how to best combine the predictions from multiple contributing ensemble member models. And as we know Ensemble methods have higher predictive accuracy, compared to the individual models. Ensemble methods are very useful when there is both linear and non-linear type of data in the dataset; different models can be combined to handle this type of data. 


