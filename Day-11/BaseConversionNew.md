# Base Conversion

## Task 1


```r
toBase <- function(z, b) {
    z <- z
    sofar <- c()
    repeat {
        r <- z%%b
        sofar <- c(r, sofar)
        z <- (z - r)/b
        if (z == 0) 
            break
    }
    return(as.character(sofar))
}
```


*Test Statements*

```r
toBase(z = 10, b = 2)
```

```
## [1] "1" "0" "1" "0"
```

