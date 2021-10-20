# Time-Series-Forecasting-Yahoo-Stock-Price
Size of Dataset:  7 columns and 1825 rows
Details of columns:
1.	Date: trading date
2.	High: the high and low refer to the maximum and minimum prices in a given time period.
3.	Low: the high and low refer to the maximum and minimum prices in a given time period. Open and close are the prices at which a stock began and ended trading in the same period
4.	Open: Open and close are the prices at which a stock began and ended trading in the same period
5.	Close: Open and close are the prices at which a stock began and ended trading in the same period
6.	Volume: Volume is the total amount of trading activity
7.	Adj Close: Adjusted values factor in corporate actions such as dividends, stock splits, and new share issuance
 
Model Used: The AutoRegressive Integrated Moving Average (ARIMA) model
A famous and widely used forecasting method for time-series prediction is the AutoRegressive Integrated Moving Average (ARIMA) model. ARIMA models are capable of capturing a suite of different standard temporal structures in time-series data.
Terminology
Let’s break down these terms:
•	AR: < Auto Regressive > means that the model uses the dependent relationship between an observation and some predefined number of lagged observations (also known as “time lag” or “lag”).
•	I:< Integrated > means that the model employs differencing of raw observations (e.g. it subtracts an observation from an observation at the previous time step) in order to make the time-series stationary.MA:
•	MA: < Moving Average > means that the model exploits the relationship between the residual error and the observations.
Model parameters
The standard ARIMA models expect as input parameters 3 arguments i.e. p,d,q.
•	p is the number of lag observations.
•	d is the degree of differencing.
•	q is the size/width of the moving average window
But before applying ARIMA, we need to check for auto-correlation. Thus, taking lag = 3, we plot auto-correlation.


 
Since, auto-correlation exists, thus we can apply the ARIMA model here.
For the training and test data division:
Let’s divide the data into a training (70 %) and test (30%) set. For this code we select the following ARIMA parameters: p=4, d=1 and q=0.
Summary of the code
•	We split the training dataset into train and test sets and we use the train set to fit the model, and generate a prediction for each element on the test set.
•	A rolling forecasting procedure is required given the dependence on observations in prior time steps for differencing and the AR model. To this end, we re-create the ARIMA model after each new observation is received.
•	Finally, we manually keep track of all observations in a list called history that is seeded with the training data and to which new observations are appended at each iteration.

Testing Mean Squared Error is 1851.0071852429596
The MSE of the test set is quite large denoting that the precise prediction is a hard problem. However, this is the average squared value across all the test set predictions. Let’s visualize the predictions to understand the performance of the model more.

 
