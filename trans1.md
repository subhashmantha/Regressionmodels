#Tranismissions:
#Which will save you money at the pump?

## Executive Summary

We are here to answer the question "are manual transmissions better on gas than automatic transmissions". We used a dataset from the 1974 Motor Trend US magazine, and ran some statistical tests and a regression analysis.

Although manual transmission cars in general do have higher MPG, yet, the MPG difference with the automatic ones may vary considerably, strongly affected by other characteristics like the cylinders of the engine or the total car weight.

### Data Manipulation

```r
data(mtcars)
auto <- split(mtcars, mtcars$am)[[1]]
man <- split(mtcars, mtcars$am)[[2]]
cars <- mtcars

for (i in 1:length(cars$am)) {
    if (cars$am[i] == 0) {
        cars$am[i] <- "Automatic"
    } else {
        cars$am[i] <- "Manual"
    }
}

car4 <- split(cars, cars$cyl)[[1]]
car6 <- split(cars, cars$cyl)[[2]]
car8 <- split(cars, cars$cyl)[[3]]
```


## Exploratory analysis

Looking at some simple box plots allow us to make a good judgement that manual transmissions are easier on the wallet than automatic transmissions. This first box plot shows the overall difference between automatic and manual transmissions.


