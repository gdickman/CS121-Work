
```r
displayTree <- function(tree) {
    treehelper <- function(tree, preface = "", mark = "", named = FALSE) {
        L <- length(tree)
        if (length(tree) > 0) {
            if (is.list(tree) | is.call(tree)) {
                cat(paste(preface, mark, "====>|", sep = ""))
                treehelper(tree[[1]], preface = "", named = named)  # keep it on the same line.
                # preface <- paste(preface,' |',sep='')
                
                if (L > 1) {
                  for (k in 2:L) {
                    cat(paste(preface, "     |\n", sep = ""))
                    treehelper(tree[[k]], named = named, mark = ifelse(k == 
                      L, "|", ""), preface = paste(preface, ifelse(k == L, "     ", 
                      "     |"), sep = ""))
                  }
                }
            } else {
                separator <- ifelse(named & tree == toupper(tree), "name:", 
                  "-> ")
                cat(paste(preface, mark, separator, tree, "\n", sep = ""))
            }
        }
    }
    # Now call treehelper on the tree
    if (inherits(tree, "formula")) {
        treehelper(tree[[-1]], named = FALSE)
        # [-1] is to skip the ~
    } else treehelper(tree, named = TRUE)
}
```



```r
exampleTree <- list("MAIN", list("SECOND", "a", list("2A", "b", "c")), list("THIRD", 
    "d", list("2A", "e", "f", "g")), "h", list("FOURTH", "i", list("4A", "j", 
    "k", "l"), "m"))
```




```r
displayTree(exampleTree)
```

```
## ====>|name:MAIN
##      |
##      |====>|name:SECOND
##      |     |
##      |     |-> a
##      |     |
##      |     |====>|name:2A
##      |          |
##      |          |-> b
##      |          |
##      |          |-> c
##      |
##      |====>|name:THIRD
##      |     |
##      |     |-> d
##      |     |
##      |     |====>|name:2A
##      |          |
##      |          |-> e
##      |          |
##      |          |-> f
##      |          |
##      |          |-> g
##      |
##      |-> h
##      |
##      |====>|name:FOURTH
##           |
##           |-> i
##           |
##           |====>|name:4A
##           |     |
##           |     |-> j
##           |     |
##           |     |-> k
##           |     |
##           |     |-> l
##           |
##           |-> m
```

