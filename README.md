# Passengers traffic forecasting
Forecasting Passengers traffic using Holt-Winters and SARIMA models in Python.

In this project we will try to forecast the passengers in Athens international airport using data from 2019 onwards. Specifically, we will use **holt winters model and also SARIMA model**. The forecast horizon will be from October 2026 to September 2027 and it will be interesting to see how our model did when we compare next year the actual numbers. Keep in mind we didn’t use long time horizon forecast because that requires other metrics like GDP, tourism rates etc. but for our forecasting horizon probably with holt winters or SARIMA we have a very good approximation. That being said we cannot foresee events like COVID, and the model as we will see in the end has learned that the uncertainty in which was trained was huge and that translates later in the confidence intervals where it practically said we are not sure at all about what could go wrong and influence the total passenger numbers so the variance could be great for more distant forecasts. So, confidence intervals may not be meaningful, so we excluded from our forecast. 

Initially we plot the available monthly data we have for passenger traffic. We can see that there is clearly seasonality as we expected and a growth trend. The winter months are typically lower for Greece whereas the summer months are the strongest and August especially is the strongest month in terms of passenger traffic.

We then do a baseline to start from somewhere. That means that we will use as a reference a very simple forecast, which is no other than using each month the previous years traffic. Then we will see if our models do better than this baseline forecast, because if not there is no point in using them. If our model does better than just using the previous year traffic then we have something to continue. 

We then plot Actual vs Baseline for our test period and then calculate the forecast error for each month (Passengers - Baseline) / Passengers and then we take the mean of that. This is known as Mean Absolute Percentage Error (MAPE). So, we just found the Baseline MAPE and the next step will be to find the MAPE after we train our first model which is Holt Winters.

So we train our model using initially a seasonality and a trend . we first choose multiplicative seasonality because it makes sense, as it is in accoredance with the level which the airport has but we will have to decide if we will use trend or not. We will use additive trend initially to see how our model does and then decide if we keep it or not. 

So we fit the model in our training set and we find the α,β,γ that minimize SSE. 


