Testing Human Response Times
========================================================

```r
getData <- function(n) {
    result <- rep(NA, n)
    for (k in 1:n) {
        before <- Sys.time()
        readline("Press return:")
        after <- Sys.time()
        delay <- as.numeric(after - before)
        cat(rep("\n", 20))
        result[k] <- delay
        Sys.sleep(runif(1, min = 1, max = 5))
    }
    return(result)
}
```


*Test Statement*

```r
getData
```

```
## function(n) {
##     result <- rep(NA, n)
##     for (k in 1:n) {
##         before <- Sys.time()
##         readline("Press return:")
##         after <- Sys.time()
##         delay <- as.numeric(after - before)
##         cat(rep("\n", 20))
##         result[k] <- delay
##         Sys.sleep(runif(1, min = 1, max = 5))
##     }
##     return(result)
## }
```

