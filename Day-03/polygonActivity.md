# Blank "Canvases", Circles and Squares
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


- To create a circle, you have to plot points with the agnles of a circle

```r
circle <- function(x, y, r, ry = r, ...) {
    angs <- seq(0, 2 * pi, length = 300)
    xpts <- x + r * cos(angs)
    ypts <- y + ry * sin(angs)
    polygon(xpts, ypts, ...)
}
plot(1:2, xlim = c(0, 100), ylim = c(0, 100), type = "n", xlab = "", ylab = "")
circle(50, 50, 20, col = scales::alpha("blue", 0.3), border = "white")
circle(20, 60, 10, 40, col = scales::alpha("pink", 0.3), border = "white")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 


- The second polygon is created similarly to the square, except 5 points are plotted because it is a pentagon

```r
plot(1:2, xlim = c(0, 100), ylim = c(0, 100), type = "n", xlab = "", ylab = "")
polygon(c(58, 63, 83, 88, 73), c(85, 65, 65, 85, 95), col = "yellow", border = "NA")
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 


- The last sqaure can be drawn using the polygon() command

```r
plot(1:2, xlim = c(0, 100), ylim = c(0, 100), type = "n", xlab = "", ylab = "")
polygon(c(15, 30, 30, 15), c(45, 45, 60, 60), col = "green", border = "blue")
```

![plot of chunk unnamed-chunk-4](figure/unnamed-chunk-4.png) 


- Together on a plot, it looks like this:

```r
plot(1:2, xlim = c(0, 100), ylim = c(0, 100), type = "n", xlab = "", ylab = "")
polygon(c(20, 40, 40, 20), c(20, 20, 40, 40), col = scales::alpha("red", 0.5), 
    border = "black")
circle(50, 50, 20, col = scales::alpha("light blue", 0.4), border = NA)
circle(20, 65, 10, 20, col = scales::alpha("pink", 0.5), border = NA)
polygon(c(58, 63, 83, 88, 73), c(65, 45, 45, 65, 75), col = scales::alpha("yellow", 
    0.5), border = NA)
polygon(c(20, 45, 45, 20), c(45, 45, 70, 70), col = scales::alpha("green", 0.5), 
    border = "blue", lwd = 4)
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-5.png) 

