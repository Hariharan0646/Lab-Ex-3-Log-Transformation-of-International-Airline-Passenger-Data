# Ex-03: Log Transformation of International Airline Passenger Data
## NAME : Hariharan S
## REG NO: 2305001009
## Aim
To perform log transformation on the International Airline Passenger dataset using Python.

## Objectives
To load the airline passenger dataset.
To visualize the original time series data.
To apply log transformation using NumPy.
To compare the original and transformed time series.
To analyze variance before and after transformation.
## Program
```python
    # Step 1: Import Required Libraries
    import pandas as pd
    import numpy as np
    import matplotlib.pyplot as plt

    # Step 2: Load the Dataset
    df = pd.read_csv("AirPassengers.csv")
    df["Month"] = pd.to_datetime(df["Month"])
    df.set_index("Month", inplace=True)

    print("Original Data:")
    print(df.head())

    # Step 3: Plot Original Time Series
    plt.figure(figsize=(10, 5))
    plt.plot(df.index, df["Passengers"])
    plt.title("International Airline Passengers")
    plt.xlabel("Year")
    plt.ylabel("Passengers")
    plt.grid(True)
    plt.show()

    # Step 4: Apply Log Transformation
    df["Log_Passengers"] = np.log(df["Passengers"])
    print("Log Transformed Data:")
    print(df.head())

    # Step 5: Plot Log-Transformed Series
    plt.figure(figsize=(10, 5))
    plt.plot(df.index, df["Log_Passengers"])
    plt.title("Log-Transformed Airline Passenger Data")
    plt.xlabel("Year")
    plt.ylabel("Log(Passengers)")
    plt.grid(True)
    plt.show()

    # Step 6: Compare Original and Transformed Series
    fig, axes = plt.subplots(2, 1, figsize=(10, 8))

    axes[0].plot(df.index, df["Passengers"])
    axes[0].set_title("Original Time Series")
    axes[0].grid(True)

    axes[1].plot(df.index, df["Log_Passengers"])
    axes[1].set_title("Log-Transformed Time Series")
    axes[1].grid(True)

    plt.tight_layout()
    plt.show()

    # Step 7: Compare Variance
    print("Variance Before Transformation:", df["Passengers"].var())
    print("Variance After Transformation:", df["Log_Passengers"].var())
```
## Output
<img width="641" height="422" alt="image" src="https://github.com/user-attachments/assets/b61a2b1f-50fd-449e-b167-b4b71ac3d1e2" />
<img width="1005" height="470" alt="image" src="https://github.com/user-attachments/assets/c7442a0f-60fc-4780-8f32-305bb8f6d781" />
<img width="471" height="202" alt="image" src="https://github.com/user-attachments/assets/78a232a6-7cc2-487e-baf7-537296130344" />
<img width="1010" height="470" alt="image" src="https://github.com/user-attachments/assets/a74a4ae9-588a-4ba0-82a4-1db14684c435" />
<img width="1189" height="790" alt="image" src="https://github.com/user-attachments/assets/b15212a3-efb1-411f-9a13-2b0f1b961344" />
<img width="1189" height="790" alt="image" src="https://github.com/user-attachments/assets/df4b1ab8-9c77-4b7a-b8bd-93e35bbd2de6" />

## Result
Log transformation was successfully applied to the International Airline Passenger dataset. The original and transformed series were plotted and compared. The transformation compresses larger values and may help stabilize increasing variability.
