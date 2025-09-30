# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 30/9/2025


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```py
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
import pandas as pd

data = pd.read_csv('Crypto Data Since 2015.csv',parse_dates=['Date'],index_col='Date')

decomposition = seasonal_decompose(data['Bitcoin (USD)'], model='additive',period=12)

plt.figure(figsize=(12, 12))
decomposition.plot()

plt.subplot(411)
plt.plot(data['Bitcoin (USD)'], label='Monthly Rate')
plt.legend(loc='upper left')
plt.title('Monthly Rate')

plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()


```
















### OUTPUT:
<img width="946" height="670" alt="image" src="https://github.com/user-attachments/assets/1c22460c-e057-4f07-8726-4fc1b94cecb8" />




### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
