# MCMSEM
R-package which allows users to run multi co-moment structural equation models.

## Citation
If you use this package please include the following citation:
**#TODO: add reference**


## Installation

Currently this packge is not listed on CRAN and should therefore be installed from GitHub idrectly.
```
library(devtools)
install_github("https://github.com/matthijsz/MCMSEM")
```

## Usage

Use the `MCMSEM` function to fit MCMSEM models:
```
library(MCMSEM)
result <- MCMSEM(data)
```
Several options can be specified, such as the use of positive or negative confounding:
```
library(MCMSEM)
result_positive <- MCMSEM(data, confounding='positive')
result_negative <- MCMSEM(data, confounding='negative')
```
**#TODO: add some text about what to do when**

By default Standard Errors for each estimate are computed through bootstrap, this can be disabled
```
result <- MCMSEM(data, compute_se=FALSE)
```

If computing SE takes to long, an alternative is to reduce the number of iterations (default is 200)
```
result <- MCMSEM(data, bootstrap_iter=100)
```

To enhance performance a faster two-step bootstrap is performed by default, this can be changed if needed.
```
result <- MCMSEM(data, bootstrap_type='one-step')
```

For testing purposes, this package also includes a function to simulate data which will work directly with the `MCMSEM` function:
```
data <- simulate_data(n=500000)
result <- MCMSEM(data)
```

###Patch notes
- v0.1.0 - Initial commit