## Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
Date: 
### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
file_path = 'ECOMM DATA.csv'
data = pd.read_csv(file_path)
profit_data = data['Profit'].dropna().values
data_mean = np.mean(profit_data)
data_var = np.var(profit_data)
normalized_data = (profit_data - data_mean) / np.sqrt(data_var)
acf_result = np.correlate(normalized_data, normalized_data, mode='full')
acf_result = acf_result[len(acf_result)//2:]
plt.figure(figsize=(10, 5))
plt.stem(acf_result[:36])
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.title('Autocorrelation Function (ACF) of Profit Data')
plt.grid(True)  # Adding grid for better visibility
plt.show()
```

### OUTPUT:
![image](https://github.com/user-attachments/assets/2d117573-64b1-49c3-92a4-6335d404c32d)

### RESULT:
Thus we have successfully implemented the auto correlation function in python.
