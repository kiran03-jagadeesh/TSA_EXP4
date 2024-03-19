# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
# Date: 19/03/2024



### AIM:
To implement ARMA model in python.
### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.
### PROGRAM:
```
from pandas import read_csv
from pandas import datetime
from matplotlib import pyplot
from pandas.plotting import autocorrelation_plot
from pandas import DataFrame
from statsmodels.tsa.arima_model import ARIMA
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
from statsmodels.tsa.arima_process import ArmaProcess
import matplotlib.pyplot as plt
import numpy as np
import warnings
warnings.filterwarnings('ignore')
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['figure.figsize'] = [10, 7.5]

ar1 = np.array([1,0.33])
ma1 = np.array([1,0.9])
ARMA_1 = ArmaProcess(ar1,ma1).generate_sample(nsample = 1000)
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()
plot_acf(ARMA_1)
plot_pacf(ARMA_1)
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=10000)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()
plot_acf(ARMA_2)
plot_pacf(ARMA_2)
```
OUTPUT:
![image](https://github.com/manojvenaram/TSA_EXP4/assets/94165064/1915dec6-810e-443b-a8d2-edf04d90ef0f)
![image](https://github.com/manojvenaram/TSA_EXP4/assets/94165064/529de11f-a6e6-4c33-93c7-5e588fe2ce08)
![image](https://github.com/manojvenaram/TSA_EXP4/assets/94165064/feee07f2-112d-425a-896d-894f23407c44)
![image](https://github.com/manojvenaram/TSA_EXP4/assets/94165064/aa383e39-0207-4c2c-98c5-1a7087727c78)
![image](https://github.com/manojvenaram/TSA_EXP4/assets/94165064/10e02684-4e92-4f37-8b55-c636ec5c91b0)


RESULT:
Thus, a python program is created to fir ARMA Model successfully.
