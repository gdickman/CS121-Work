# Practing Tree Structures


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
practiceTree <- list("Animals", list("Dogs", list("Poodle", "Golden Retriever"), 
    "Cats", list("Russian Blue", "Siamese")))
```



```r
displayTree(practiceTree)
```

```
## ====>|-> Animals
##      |
##      |====>|-> Dogs
##           |
##           |====>|-> Poodle
##           |     |
##           |     |-> Golden Retriever
##           |
##           |-> Cats
##           |
##           |====>|-> Russian Blue
##                |
##                |-> Siamese
```

