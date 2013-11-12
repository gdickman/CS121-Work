Numbers and Strings
========================================================

## Outlier Function

```r
outlier <- function(x) {
    # define the state
    x <- c(0:9)
    # update the state
    outlier <- quantile(x, probs = seq(0.25, 0.75), na.rm = FALSE, names = TRUE, 
        type = 7)
    return(outlier)
}
```


## Numbers and Languages

```r
DigitToWord <- function(number, word) {
    
}
```


## Help for Crossword Puzzles

```r
LettersMatch <- function(words, pattern) {
    small <- c("case", "second", "third", "are")
    match <- grepl("^...$", small)
    return(match)
}
```



```r
LettersMatch("base", 3)
```

```
## [1] FALSE FALSE FALSE  TRUE
```

