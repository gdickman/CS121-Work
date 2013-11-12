Derivatives as Finite Differences
========================================================

## First Derivative

```r
myD <- function(f) {
    h <- 0.001
    fprime <- function(x) {
        (f(x + h) - f(x))/h
    }
    return(fprime)
}
```



```r
plot(myD(sin))
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 


## Second Derivative

```r
myD2 <- function(f) {
    h <- 0.001
    fprime <- function(x) {
        (f(x + h) - f(x))/h
    }
    ddx <- function(x) {
        (fprime(x + h) - fprime(x))/h
    }
    return(ddx)
}
```



```r
plot(myD2(sin))
```

![plot of chunk unnamed-chunk-4](figure/unnamed-chunk-4.png) 


## Alternate Second Derivative

```r
altmyD2 <- function(f) {
    h <- 0.001
    fprime <- myD(f)
    fprime2 <- myD(fprime)
    return(fprime2)
}
```



```r
plot(altmyD2(sin))
```

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6.png) 

