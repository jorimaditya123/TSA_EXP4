# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
# Date: 02-11-2026

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
```python

import numpy as np
import matplotlib.pyplot as plt

from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf

# Set figure size
plt.rcParams['figure.figsize'] = (10, 5)

# ARMA(1,1) process
ar1 = np.array([1, -0.75])
ma1 = np.array([1, 0.65])

ARMA_1 = ArmaProcess(ar1, ma1)
simulated_data_1 = ARMA_1.generate_sample(nsample=1000)

# Plot ARMA(1,1) time series
plt.figure()
plt.plot(simulated_data_1)
plt.title("Simulated ARMA(1,1) Process")
plt.xlim(0, 1000)
plt.show()

# Autocorrelation plot
plot_acf(simulated_data_1, lags=40)
plt.title("Autocorrelation - ARMA(1,1)")
plt.show()

# Partial autocorrelation plot
plot_pacf(simulated_data_1, lags=40, method='ywm')
plt.title("Partial Autocorrelation - ARMA(1,1)")
plt.show()


# ARMA(2,2) process
ar2 = np.array([1, -0.5, 0.25])
ma2 = np.array([1, 0.4, 0.3])

ARMA_2 = ArmaProcess(ar2, ma2)
simulated_data_2 = ARMA_2.generate_sample(nsample=10000)

# Plot ARMA(2,2) time series
plt.figure()
plt.plot(simulated_data_2)
plt.title("Simulated ARMA(2,2) Process")
plt.xlim(0, 10000)
plt.show()

# Autocorrelation plot
plot_acf(simulated_data_2, lags=40)
plt.title("Autocorrelation - ARMA(2,2)")
plt.show()

# Partial autocorrelation plot
plot_pacf(simulated_data_2, lags=40, method='ywm')
plt.title("Partial Autocorrelation - ARMA(2,2)")
plt.show()

```

### OUTPUT:

SIMULATED ARMA(1,1) PROCESS:

<img width="922" height="496" alt="image" src="https://github.com/user-attachments/assets/68682c83-5508-4bf6-9cc6-d886549d1c8a" />

Partial Autocorrelation

<img width="931" height="495" alt="image" src="https://github.com/user-attachments/assets/a7ca7be6-c6c2-49f9-9481-cb2dcfab7e38" />

Autocorrelation

<img width="943" height="489" alt="image" src="https://github.com/user-attachments/assets/e74fd54c-fd95-487b-a3c3-329fb9d273f0" />

SIMULATED ARMA(2,2) PROCESS:

<img width="931" height="489" alt="image" src="https://github.com/user-attachments/assets/8c2f2c34-5397-463a-8949-343e4170aa81" />

Partial Autocorrelation

<img width="934" height="481" alt="image" src="https://github.com/user-attachments/assets/99e7e1af-3194-4ea3-80ba-42eba69187c2" />

Autocorrelation

<img width="961" height="475" alt="image" src="https://github.com/user-attachments/assets/f690b348-9f6e-4388-989e-ed84b056fd70" />

### RESULT:
Thus, a python program is created to fir ARMA Model successfully.
