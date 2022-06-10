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


