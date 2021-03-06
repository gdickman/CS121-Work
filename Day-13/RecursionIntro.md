# Recursion

## fibLoop

```r
fibLoop <- function(n) {
    if (n < 0 | round(n) != n) {
        warning("Invalid")
        return(NA)
    }
    sofar <- rep(1, n + 1)
    sofar[2] <- 1
    for (k in 3:n) {
        sofar[k] <- sofar[k - 1] + sofar[k - 2]
    }
    return(sofar[k])
}
```


## Test

```r
fibLoop(6)
```

```
## [1] 8
```


## fibRecurse

```r
fibRecurse <- function(n) {
    if (n == 1) {
        return(1)
    } else {
        if (n == 0) 
            return(0)
    }
    fibRec <- fibRecurse(n - 1) + fibRecurse(n - 2)
    return(fibRec)
}
```



## addNSeq

```r
addNseq <- function(x) {
    if (x < 2) 
        return(x)
    return(x + addNseq(x - 1))
}
```


## Test

```r
addNseq(10)
```

```
## [1] 55
```


## addRecursively

```r
addRecursively <- function(v) {
    if (length(v) == 1) 
        return(v) else {
        c(v[1] + addRecursively(v[-1]))
    }
}
```


## Tests

```r
addRecursively(1:10)
```

```
## [1] 55
```

```r
addRecursively(c(1, 2, 3, 4))
```

```
## [1] 10
```


## addNSeqlooping

```r
addNSeqlooping <- function(n) {
    res <- 0
    for (k in 1:n) {
        res <- res + k
    }
    return(res)
}
```


## Test

```r
addNSeqlooping(7)
```

```
## [1] 28
```


## addRecursively Lopp

```r
addRecLoop <- function(n) {
    res <- 0
    for (k in 1:length(n)) {
        res <- res + n[k]
    }
    return(res)
}
```


## Test

```r
addRecLoop(c(1, 2, 3))
```

```
## [1] 6
```

```r
addRecLoop(1:6)
```

```
## [1] 21
```


## addNseq No Loop

```r
addnoloop <- function(n) {
    return(sum(n:0))
}
```


## Test

```r
addnoloop(6)
```

```
## [1] 21
```


## addRecursively No Loop

```r
addRec2 <- function(n) {
    return(sum(n))
}
```


## Test

```r
addRec2(1:15)
```

```
## [1] 120
```


## SimpleRiemann

```r
simpleRiemann <- function(f, a = 0, b = 1, n = 3) {
    rectangleWidth = (b - a)/n
    midpoints <- seq(a + rectangleWidth/2, b - rectangleWidth/2, length = n)
    rectangleAreas <- sapply(midpoints, f) * rectangleWidth
    return(sum(rectangleAreas))
}
```


## integrateRiemann

```r
integrateRiemann <- function(f, a = 0, b = 1) {
    nbins <- 5
    bigBins <- simpleRiemann(f, a = a, b = b, n = nbins)
    for (k in 1:5) {
        nbins <- nbins * 10  # much smaller bins
        smallBins <- simpleRiemann(f, a = a, b = b, n = nbins)
        if (abs(smallBins - bigBins) < 1e-05) 
            break
        bigBins <- smallBins
    }
    return(smallBins)
}
```


## integrateRecursive

```r
integrateRecursive <- function(f, a = 0, b = 1, lim = 1e-05, origwidth = b - 
    a) {
    bigBins <- simpleRiemann(f, a = a, b = b, n = 5)
    smallBins <- simpleRiemann(f, a = a, b = b, n = 10)
    if (abs(bigBins - smallBins) < lim) {
        return(smallBins)
    } else {
        if ((b - a) < origwidth/10000) {
            warning("Hit integration limit")
            return(smallBins)
        }
        
        mid <- (a + b)/2
        total <- integrateRecursive(f, a = a, b = mid, lim = lim, origwidth = origwidth) + 
            integrateRecursive(f, a = mid, b = b, lim = lim, origwidth = origwidth)
        return(total)
    }
}
```


## Tests

```r
integrateRecursive(function(x) 5 * x, 0, 2)
```

```
## [1] 10
```

$\int_0^2 5xdx = 2.5x^2|_0^2 = 10$ 


```r
integrateRecursive(function(x) {
    sin(1/x)
}, 0, 1)
```

```
## Warning: Hit integration limit Warning: Hit integration limit Warning: Hit
## integration limit Warning: Hit integration limit Warning: Hit integration
## limit Warning: Hit integration limit Warning: Hit integration limit
## Warning: Hit integration limit Warning: Hit integration limit Warning: Hit
## integration limit Warning: Hit integration limit Warning: Hit integration
## limit Warning: Hit integration limit Warning: Hit integration limit
## Warning: Hit integration limit Warning: Hit integration limit
```

```
## [1] 0.5043
```

$\int_0^(1) sin(frac{1}{x})dx = 0.5041$
