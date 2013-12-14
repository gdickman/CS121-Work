Tool Tips
========================================================

## formatWord Function

```r

formatWord <- function(word, trans, class1) {
    if (is.na(trans)) 
        return(word)
    test1 <- paste("<span class='", class1, "' ", sep = "")
    test2 <- paste(test1, "title='", trans, "'>", sep = "")
    test3 <- paste(test2, word, "</span>", sep = "")
    return(test3)
}
```


## Testing

```r
cat(formatWord("Hello", "hi there!", "hiword"))
```

<span class='hiword' title='hi there!'>Hello</span>

```r

cat(formatWord("Hello", "hi there!", class = "hiword"), "to", "all", "of", "you", 
    "in", formatWord("Television Land.", "TV Viewers", "hiword"))
```

<span class='hiword' title='hi there!'>Hello</span> to all of you in <span class='hiword' title='TV Viewers'>Television Land.</span>


## FormatString Function

```r
formatString <- function(word, tips, styles) {
    results <- c()
    for (k in 1:length(word)) {
        results[k] <- formatWord(word[k], tips[k], styles[k])
    }
    return(cat(results))
}
```


## Testing

```r
formatString(c("How", "now", "brown", "cow", "!"), c("How are you doing?", NA, 
    "Why brown?", "bovine", "enthusiasm"), c("hiword", "", "brown", "blue", 
    "hiword"))
```

<span class='hiword' title='How are you doing?'>How</span> now <span class='brown' title='Why brown?'>brown</span> <span class='blue' title='bovine'>cow</span> <span class='hiword' title='enthusiasm'>!</span>
