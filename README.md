# Regularization

Overfitting is when our model performs exceptionally wel on training data and its performance on testing data is very bad. To deal with this problem we add some biad to our model ourselves.

### Question : What regularization exactly does?
### Answer : Loss function is added with an extra term of bias. This results in lower values of slopes for the features. Due to reduced slope, effect of change in independent variables on dependent variables reduces. In other terms depedent variable becomes less sensitive towards changes made in indepenedent variables. This also means that due to addition of penalty term, the loss function curve shifts upwards and values on m axis are damped. Due to this shifted new curve, new optimum value of slope is ruduced, and loss value at this new point is lower than what it was in the pure loss fucntion curve. This increase in optimum value on loss fucntion causes a small incremenet in the errors for training data.

Types of regularization-
1. Ridge regression.
2. Lasso regression.
3. Elasticnet regression.


# Ridge regression

![WhatsApp Image 2022-06-10 at 1 25 00 PM](https://user-images.githubusercontent.com/92416952/173024427-554b908e-e07e-499d-8711-34006545e3d2.jpeg)


## 5 Key points about Ridge regression:
### (1) How the coefficients are affected.
As we start increasing the value of shrinkage coefficient, all the coefficient values associated with the features start to shrink. These variables shrink nearly to zero, but never become equal to zero. Hence for a large value of sheinkage coefficient, slope values shrink to a large extent, but never become equal to zero.
### (2) Higher slope values are impacted more.
Higher values of slope shrink more with increasing values of shrinkage coeffiecnt. In ither words, higher slope valuea are penalized to a larger extent.
### (3)  How regularization affects bias and varinace ?
For lower values of shrinkage coefficients, bias is very low and variance is very high.
For higher values of shrinkage coefficinets, bias is very hugh and ariance is lower than that was in previous case.
For optimum values of shrinkgae coefficinets, both bias and variance have best values.
![WhatsApp Image 2022-06-10 at 1 52 38 PM](https://user-images.githubusercontent.com/92416952/173026479-da04cc93-29f2-43ce-b903-cd79b232c15d.jpeg)
### (4) Impact on loss fucntion
As the value of shrinkage coefficient increases, loss function shifts upwards. And the beat slope value shifts towards lower values.
In case of single Independent variable and single dependent variable.
![WhatsApp Image 2022-06-10 at 1 53 15 PM](https://user-images.githubusercontent.com/92416952/173026648-d1525962-6148-4c19-b167-e895785be849.jpeg)
In case of single dependent variable and two independent variables, we can observe how loss function curve shifts upwards in 3D.
![WhatsApp Image 2022-06-10 at 1 53 50 PM](https://user-images.githubusercontent.com/92416952/173026664-ae922eef-ce0b-4c45-a0f7-a4c83e59bd64.jpeg)
### (5) Why is it called ridge?
As our shrikage coefficient increases, our plot starts to shift upwards. Due to the penalty term, a circle is formed. With increasing shrikage coefficient, at one point the lowest point point on the loss function touches the circle formed by the penalty term. As our solution, i.e. 'z' point always lies on boundary or ridge of circle formed by ridege penalty factor, this regression type is called ridge regression.
![WhatsApp Image 2022-06-10 at 1 55 26 PM](https://user-images.githubusercontent.com/92416952/173027297-5ffafb5c-f53e-4a06-a2ae-c9e0680fc3f9.jpeg)
![WhatsApp Image 2022-06-10 at 1 55 56 PM](https://user-images.githubusercontent.com/92416952/173027313-62ad2657-fadf-495e-a9e4-32965055c2b4.jpeg)


# Lasso regression
Here if we increase the shrinkage coefficient, unlike ridge regression, in lasso regression, the values of slope coefficients can attain the value zero. Due to this the features which are less important for decsion making bacome zero for a sufficiently high value of shrikage coefficient. This means we can do feature selection using Lasso regression. If we are using high dimantional data and some of the columns are irrelevant, then we should use lasso. Because lasso will inherently do feature selection and slope values less important features become zero.


## 5 Key points about Lasso regression:
### (1) How the coefficients are affected.
If we gp on increasing the shrinkage coefficient value, we observe that the slope values for tthe less important features become zero. If we further increase the shrinkage coefficient value, slope value for all the coefficent will vecome zero and we will be left only with y_intercept value. This will be case of underfitting.
### (2) Higher slope values are impacted more.
Higher values of slope shrink more with increasing values of shrinkage coeffiecnt. In ither words, higher slope values are penalized to a larger extent.
### (3) Impact of increasing shrinkage coefficient on bias and variance
![WhatsApp Image 2022-06-10 at 1 52 38 PM](https://user-images.githubusercontent.com/92416952/173052666-f0eadb2d-3f2f-4e43-94e7-8fc5e6b30619.jpeg)
### (4) Effect of regularization on loss function.
As we increase the value of shrinkage coefficent, for lasso regression, we observe that for each feature's slope coefficient value an edge starts to form at β=0. 
Afetr a certain value of shrinkage coefficient, this edge point at β=0 becomes point of minimum loss. This means that after this point, slope values corresponding to this feature becomes zero. And this feature no longer affects value of dependent variable. Say after shrinkga ecoefficient=1000 , this slope value for this feature becomes zero, meaning this feature no longer helps in predicting the value of dependent variable for a given input.

### (5) Why is this edge forming ? Why lasso regression is creating sparcity ? Why ridege regression cannot create sparcity?
![WhatsApp Image 2022-06-10 at 4 41 33 PM](https://user-images.githubusercontent.com/92416952/173053067-69b544e7-381b-4ab3-9fb3-2883759c6094.jpeg)
a) In the OLS formula for slope value for Ridge regression, the  λ value is in denominator. Hence by increasing  λ to a large value, we can make the slope value nearly equal to zero, but can never make it equal to zero.  
![WhatsApp Image 2022-06-10 at 6 06 31 PM](https://user-images.githubusercontent.com/92416952/173065608-6c2cd2d5-6d8b-40e9-b1e2-025aa4e48eab.jpeg)
b) In the OLS formula for lasso regression,  λ value is in numerator. This means by tweaking the value of  λ we can make the whole slope value = zero.
![WhatsApp Image 2022-06-10 at 6 06 58 PM](https://user-images.githubusercontent.com/92416952/173065881-a2abf433-4b22-4a87-8086-a558d857c446.jpeg)

In case of lasso regression, this becomes a multi case problem, where the value of slopes can be >0 OR =0 OR <0.
case 1 formula (slope value is positive)
![WhatsApp Image 2022-06-10 at 6 19 30 PM](https://user-images.githubusercontent.com/92416952/173067990-e26bac4a-9302-42fc-9226-4d0c48c30f05.jpeg)

case 2 formula (slope value = zero)
![WhatsApp Image 2022-06-10 at 6 19 59 PM](https://user-images.githubusercontent.com/92416952/173068086-5a012f80-1cd9-4e1d-af64-c1280bb86f63.jpeg)

case 3 formula (slope value is negative)
![WhatsApp Image 2022-06-10 at 6 20 18 PM](https://user-images.githubusercontent.com/92416952/173068103-db98fb31-2e7d-4822-bb6a-9c87840b2dd2.jpeg)

We can observe from the formula that the slope value in lasso regression can become zero. The presence of three cases where slope <0 AND slope=0 AND slope>0, sudden change in the formula for slope causes the slope value to drastisticallly change at β=0 forming an edge shape. This leads to formation of edge in the plot at β=0.




# ElasticNet regression

Elastic net regression is a combination of Ridge regressiona dn Lasso regression.
![WhatsApp Image 2022-06-10 at 6 26 08 PM](https://user-images.githubusercontent.com/92416952/173069062-26a44c19-cf9b-437d-9d72-807019a3530d.jpeg)


### When do we need to use ElasticNet regression?
If our dataset contains a large nu ber of columns and we cannot tell if some of the columns or all of the columns are irrelevent for finding the predicted value of dependent variable. If our dataset is large and multicollinearity is present in the dataset, Elasticnet regression is preferred. In such cases we use ElasticNet regression.
### Hyperparameters to be specified for elasticnet regression.
1. λ
2. l1_ratio
