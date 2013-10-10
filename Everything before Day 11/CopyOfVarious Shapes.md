# Various Shapes
========================================================

- To create a plot, use the command plot()


```r
plot(1:2, xlim = c(0, 100), ylim = c(0, 100), type = "n", xlab = "", ylab = "")
```

![plot of chunk plot](figure/plot.png) 


- To create a polygon, use the command polygon()


```r
plot(1:2, xlim = c(0, 100), ylim = c(0, 100), type = "n", xlab = "", ylab = "")
polygon(c(25, 35, 35, 25), c(25, 25, 35, 35), col = "red", border = "black")
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-1.png) 


- In order to create a circle, install the poltrix package, and use the command draw.circle()

```r
plot(1:2, xlim = c(0, 100), ylim = c(0, 100), type = "n", xlab = "", ylab = "")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

```r
draw.circle(50, 50, 20, 20, nv = 100, border = "NA", col = "lightblue")
```

```
## Error: could not find function "draw.circle"
```


- The second polygon is created similarly to the square, except 5 points are plotted because it is a pentagon

```r
plot(1:2, xlim = c(0, 100), ylim = c(0, 100), type = "n", xlab = "", ylab = "")
polygon(c(58, 63, 83, 88, 73), c(85, 65, 65, 85, 95), col = "yellow", border = "NA")
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 


- An ellipse can be drawn using the draw.ellipse() command from the plotrix package

```r
plot(1:2, xlim = c(0, 100), ylim = c(0, 100), type = "n", xlab = "", ylab = "")
```

![plot of chunk unnamed-chunk-4](figure/unnamed-chunk-4.png) 

```r
draw.ellipse(20, 60, 10, 25, col = "lightpink", border = "NA")
```

```
## Error: could not find function "draw.ellipse"
```


- The last sqaure can be drawn using the polygon() command

```r
plot(1:2, xlim = c(0, 100), ylim = c(0, 100), type = "n", xlab = "", ylab = "")
polygon(c(15, 30, 30, 15), c(45, 45, 60, 60), col = "green", border = "blue")
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-5.png) 


- Together on a plot, it looks like this:

```r
plot(1:2, xlim = c(0, 100), ylim = c(0, 100), type = "n", xlab = "", ylab = "")
polygon(c(25, 35, 35, 25), c(25, 25, 35, 35), col = "red", border = "black")
draw.circle(50, 50, 20, 20, nv = 100, border = "NA", col = "lightblue")
```

```
## Error: could not find function "draw.circle"
```

```r
polygon(c(58, 63, 83, 88, 73), c(85, 65, 65, 85, 95), col = "yellow", border = "NA")
draw.ellipse(20, 60, 10, 25, col = "lightpink", border = "NA")
```

```
## Error: could not find function "draw.ellipse"
```

```r
polygon(c(15, 30, 30, 15), c(45, 45, 60, 60), col = "green", border = "blue")
```

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6.png) 


