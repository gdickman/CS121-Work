Blastoff Exercise
========================================================


```r
blastoffWhile <- function(time) {
    while (time != 0) {
        Sys.sleep(1)
        cat(time, "\n")
        time <- time - 1
    }
    Sys.sleep(1)
    cat("Blastoff!")
}
```


*Test Statement*

```r
blastoffWhile(5)
```

```
## 5 
## 4 
## 3 
## 2 
## 1 
## Blastoff!
```

