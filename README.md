# Ex.No: 01A PLOT A TIME SERIES DATA
### Date:12.08.2025
## NAME:KEERTHIKA M P
## REG NO:212223240071

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("laptop_price.csv", encoding="latin1")

df['Date'] = pd.date_range(start="2020-01-01", periods=len(df), freq="M")

df['Date'] = pd.to_datetime(df['Date'])

df.set_index('Date', inplace=True)

mean_price = df['Price_euros'].mean()
print(f"Average Laptop Price: €{mean_price:.2f}")

plt.figure(figsize=(10, 6))
plt.plot(df.index, df['Price_euros'], marker='o', linestyle='-', label='Laptop Price')
plt.axhline(y=mean_price, color='red', linestyle='--', label='Average Price')

plt.title("Laptop Price Trend Over Time")
plt.xlabel("Date")
plt.ylabel("Price (€)")
plt.legend()
plt.grid(True)
plt.show()

```
# OUTPUT:

<img width="940" height="551" alt="image" src="https://github.com/user-attachments/assets/121b0b7a-15a6-471f-96c5-5dda6528e0fc" />







# RESULT:
Thus we have created the python code for plotting the time series of given data.
