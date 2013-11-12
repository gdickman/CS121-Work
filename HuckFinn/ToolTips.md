Tool Tips
========================================================
## formatWord Function

```r
formatWord <- function(word, translation, class) {
    if (is.na(translation) == TRUE) 
        return(as, character(word)) else {
        paste("<span class=' ", class, "', title='", translation, "'>", word, 
            "</span>")
    }
}
```


# Test Case

```r
cat(formatWord("Hello", "hi there!", class = "hiword"))
```

<span class='  hiword ', title=' hi there! '> Hello </span>



```r
cat(formatWord("Hello", "hi there!", class = "hiword"), "to", "all", "of", "you", 
    "in", formatWord("Television Land.", "TV viewers", class = "hiword"))
```

<span class='  hiword ', title=' hi there! '> Hello </span> to all of you in <span class='  hiword ', title=' TV viewers '> Television Land. </span>

