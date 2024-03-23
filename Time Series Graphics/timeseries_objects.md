A time series can be thought of as a list of numbers (the measurements), along with some information about what times those numbers were recorded (the index). This information can be stored as a pandas timeseries object in python.

### The index variable

Suppose you have annual observations for the last few years:

![image](https://github.com/Hg03/forecasting_principles/assets/69637720/38a1f6cd-c625-4528-bae8-f1c2fa630bf3)

We turn this into a tsibble object using the pandas dataframe function and setting index:

```python
import pandas as pd

# Define the data
data = {
    'Year': range(2015, 2020),
    'Observation': [123, 39, 78, 52, 110]
}

# Create a DataFrame
df = pd.DataFrame(data)

# Set the 'Year' column as the index
df.set_index('Year', inplace=True)

# Display the DataFrame
print(df)

```
In Python, pandas DataFrame objects are similar to tidy data frames in R. We can extend them to incorporate temporal structure by setting a time series index. In the provided code, we set the 'Year' column as the index, establishing an association between the measurements ('Observation') and the time of recording ('Year').

For observations that are more frequent than once per year, we need to use a time class function on the index. For example, suppose we have a monthly dataset z:

```
z
#> # A dataframe: 5 × 2
#>   Month    Observation
#>   <chr>          <dbl>
#> 1 2019 Jan          50
#> 2 2019 Feb          23
#> 3 2019 Mar          34
#> 4 2019 Apr          30
#> 5 2019 May          25
```

This can be converted to a df object using the following code:



