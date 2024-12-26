inomaly: an automation for filling blank data
=====================================================================================================

*Solution for big data*

`inomaly` is an R package which contains:

R function for anomaly detection, filling in loss values of a variable from one data frame with the values from another variable, checking outliers then replacing them with other value or mean vector.

Installation
------------

``` r
install.packages("devtools")
devtools::install_github("irwannafly/inomaly")
```




Example
------------

`FillIn` is function for filling missing values, 
`outliersZ` is function for checking outlier.


Create data set with missing values as follow.
``` r
naDF <- data.frame(a = sample(c(1,2), 100, rep=TRUE), 
                   b = sample(c(3,4), 100, rep=TRUE), 
                 fNA = sample(c(100, 200, 300, 400, NA), 100, rep=TRUE))
```
Create full dataset
``` r
fillDF <- data.frame(a = c(1,2,1,2), 
                     b = c(3,3,4,4),
                 fFull = c(100, 200, 300, 400))
```
Fill in missing f's from naDF with values from fillDF
``` r
FilledInData <- FillIn(naDF, fillDF, Var1 = "fNA", Var2 = "fFull", KeyVar = c("a", "b"))
```
``` r
df$column1<-outliersZ(df$column1, zCutOff = 1.96, replace = NA, values = FALSE, digits = 4)
```



