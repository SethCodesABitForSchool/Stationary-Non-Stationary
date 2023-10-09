# Stationary-Non-Stationary
Synthetic time series with a constant mean and variance and then modify it to introduce non-stationarity.
# Load required libraries
install.packages("ggplot2")
library(ggplot2)
library(tseries)

# Set seed for reproducibility
set.seed(123)

# Generate a stationary time series
stationary_series <- rnorm(100, mean = 0, sd = 1)

# Plot the stationary time series
ggplot(data.frame(x = 1:100, y = stationary_series), aes(x, y)) +
  geom_line() +
  labs(title = "Stationary Time Series")
  
![f2ec5d91-0c0a-439d-8173-fc33109d8d01](https://github.com/SethCodesABitForSchool/Stationary-Non-Stationary/assets/147195203/82320b8d-4252-44f6-8221-15bb80621040)


# Perform ADF test for stationarity
adf_test_stationary <- adf.test(stationary_series)
print(adf_test_stationary)

# Introduce a trend
non_stationary_series <- seq(1, 100, length.out = 100) + rnorm(100, mean = 0, sd = 1)

# Plot the non-stationary time series
ggplot(data.frame(x = 1:100, y = non_stationary_series), aes(x, y)) +
  geom_line() +
  labs(title = "Non-Stationary Time Series")

![c4d157ce-4e18-4ae3-9965-b49716d07c65](https://github.com/SethCodesABitForSchool/Stationary-Non-Stationary/assets/147195203/fe4a5f5e-7d54-4a48-9ed6-fac4ad011e5f)


# Perform ADF test for stationarity
adf_test_non_stationary <- adf.test(non_stationary_series)
print(adf_test_non_stationary)


# Create a 1x2 layout
par(mfrow = c(1, 2))

# Plot the stationary time series
plot(1:100, stationary_series, type = 'l', main = "Stationary Time Series")

# Plot the non-stationary time series
plot(1:100, non_stationary_series, type = 'l', main = "Non-Stationary Time Series")

# Reset the layout to the default (1x1)
par(mfrow = c(1, 1))




![d45ce141-de04-43b4-bf1f-ab022cb8e611](https://github.com/SethCodesABitForSchool/Stationary-Non-Stationary/assets/147195203/0c71c6e4-6325-49b8-8c17-d565aeba2471)


