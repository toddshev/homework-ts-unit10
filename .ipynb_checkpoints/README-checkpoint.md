# Homework-Time Series-Unit 10

 * The initial model reduces the source data to only include Yen exchange rates since 1990.
 It then applies a Hodrick-Prescott filter to separate the trend from the noise.
 The noise is homeskedastic, adding validity to the trend component.

 * The second and third models are ARMA and ARIMA, respectively, and used for forecasting.
 The ARMA model is not a great predictor due to its high P value.  This is likely due to
 the nature of the dataset, with several peaks and troughs and having several modes.
 The forecast shows a steep decline followed by slight upticks.
 The ARIMA model is better than the ARMA model, with lower (though still high) P values.
 The forecast is choppier, but has more of an early uptick which seems more likely rather
 than a major decline, so this model would be a better option than the ARMA model.

 * The GARCH model measures the stationarity of the error.  In this case the omega and alpha(1)
 lag have low P values.  However, the alpha(2) lag adds little if any value to the model.
 According to the model, volatility is expected to increase over the next 5 days.  Note this is
 irrespective of the direction.

 * The regression models require more dataframe modifications - Source data was truncated to 1990 to present
 Then settle returns were added, multiplied by 100 for consistency, and NaNs and .inf's were dropped.
 Lastly, the lagged return was added. Then the train-test split was applied, preparing for the SKLearn
 linear regression.  Regression uses the model, fit, predict pattern.  
 Despite a lot of training data, the model had some fairly large divergences.  However, overall it did a fairly
 good job of predicting over the time period of the forecast.  With a low RMSE, and lower out-of-sample RMSE,
 this model appears to be valid.
