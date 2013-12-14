# Oct 1 2013

## Reverser

```r
Reverser <- function(x) {
    L <- strsplit(x, "")[[1]]
    R <- L[rev(1:nchar(x))]
    paste(R, collapse = "")
}
```



```r
Reverser("turck")
```

```
## [1] "kcrut"
```


## Scrambler

```r
Scrambler <- function(x) {
    S <- strsplit(x, "")[[1]]
    Q <- S[sample(1:nchar(x))]
    paste(Q, collapse = "")
}
```



```r
Scrambler("hello")
```

```
## [1] "lehol"
```


## VowelBleeper

```r
VowelBleeper <- function(word) {
    gsub("[aeiouAEIOU]", "*", word)
}
```



```r
VowelBleeper("Elephant")
```

```
## [1] "*l*ph*nt"
```


## L33t

```r
L33t <- function(x) {
    one <- gsub("[Ee]", "3", x)
    two <- gsub("[Oo]", "0", one)
    three <- gsub("[Ss]", "5", two)
    gsub("[Gg]", "9", three)
}
```



```r
L33t("graces")
```

```
## [1] "9rac35"
```


## Cypher

```r
cypher <- function(input) {
    cypher <- chartr("abcdefghijklmnopqrstuvwxyz", "mnopqrstuvwxyzabcdefghijkl", 
        input)
    return(cypher)
}
```



```r
cypher("dogz")
```

```
## [1] "pasl"
```

