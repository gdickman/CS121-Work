Recursion
========================================================


```r
addEm <- function(v) {
    sum <- 0
    for (k in 1:length(v)) {
        sum <- sum + v[k]
    }
    sum(v)
    return(sum)
}
```



```r
newAddEm <- function(v) {
    # Base Case
    if (length(v) == 0) 
        return(0)
    return(v[1] + newAddEm(v[-1]))
}
```

