Substitution Cypher
========================================================


## Step 1, the Key

```r
key <- "zoo"
first <- function(L) {
    which(L == letters)
}
paste(sapply(unlist(strsplit(key, split = NULL)), FUN = first), collapse = "")
```

```
## [1] "261515"
```



```r
first("zoo")
```

```
## integer(0)
```


## Step 2, the Cypher

```r
set.seed(paste(sapply(unlist(strsplit(key, split = NULL)), FUN = first), collapse = ""))
characters <- c(letters, LETTERS, ".", ":", ",", ";", 0:9)
fromandto <- sample(characters)
fromandto
```

```
##  [1] "q" "z" "j" ":" "D" "s" "i" "F" "y" "a" "8" "W" "K" "O" "f" "k" "d"
## [18] "u" "L" "," "P" "l" "Q" "E" "C" "Z" "A" "n" "G" "X" "g" "o" "b" "S"
## [35] "J" "m" "V" "v" "7" "H" "e" "Y" "6" "4" "5" "0" "2" "U" "1" "r" "t"
## [52] "w" "h" ";" "p" "M" "9" "x" "3" "I" "R" "c" "T" "." "B" "N"
```


## Step 3, the Encryption

```r
encrypt <- chartr(paste(characters, collapse = ""), paste(fromandto, collapse = ""), 
    "Cannot read this")
encrypt
```

```
## [1] "GqOOf, uDq: ,FyL"
```


## Step 4, the Decryption

```r
decoded <- chartr(paste(fromandto, collapse = ""), paste(characters, collapse = ""), 
    encrypt)
decoded
```

```
## [1] "Cannot read this"
```


## The Paragraph

```r
paragraph <- chartr(paste(characters, collapse = ""), paste(fromandto, collapse = ""), 
    "Many many sentences which you will not be able to read.  This class has now taught me to encrypt things, which actually makes me feel like a spy.  Possibly I could use this in the CIA? I would never work for the CIA, I am not sneaky enough.")
paragraph
```

```
## [1] "7qOC KqOC LDO,DOjDL QFyjF CfP QyWW Of, zD qzWD ,f uDq:h  0FyL jWqLL FqL OfQ ,qPiF, KD ,f DOjuCk, ,FyOiLp QFyjF qj,PqWWC Kq8DL KD sDDW Wy8D q LkCh  YfLLyzWC J jfPW: PLD ,FyL yO ,FD GJA? J QfPW: ODlDu Qfu8 sfu ,FD GJAp J qK Of, LODq8C DOfPiFh"
```

```r

decoded <- chartr(paste(fromandto, collapse = ""), paste(characters, collapse = ""), 
    paragraph)
decoded
```

```
## [1] "Many many sentences which you will not be able to read.  This class has now taught me to encrypt things, which actually makes me feel like a spy.  Possibly I could use this in the CIA? I would never work for the CIA, I am not sneaky enough."
```

