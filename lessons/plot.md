# 6. Plotting things with built in plot function
Using the plot function to plot a point

```r
plot(1, 3)
```

The plot() function accepts other parameters, such as main, xlab and ylab if you want to customize the graph with a main title and different labels for the x and y-axis. You can also use : to plot with a range of numbers instead of just specific points.

```r
plot(1:10, main="My Graph", xlab="The x-axis", ylab="The y axis")
```

To display more than one line in a graph, use the plot() function together with the lines() function:

```r
line1 <- c(1,2,3,4,5,10)
line2 <- c(2,5,7,8,9,10)

plot(line1, type = "l", col = "blue")
lines(line2, type="l", col = "red")
```

Barplot example

```r
# x-axis values
x <- c("A", "B", "C", "D")

# y-axis values
y <- c(2, 4, 6, 8)

barplot(y, names.arg = x)
```

## 7. Plotting things with ggplot

```r
mpg
View(mpg) # View the data

ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy))     # Create a simple plot

#ggplot(data = <DATA>) +
  #<GEOM_FUNCTION>(mapping = aes(<MAPPINGS>))

# Adding color to the points
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy, color = class))
```

Other ones to try are alpha, shape, and size. Just replace color with those terms.


```r
ggplot(data = mpg) +
  geom_smooth(mapping = aes(x = displ, y = hwy))
```

This plot creates a smooth line instead of a plot with all of the points on it. The line will represent all of the points.

```r
ggplot(data = mpg, mapping = aes(x = displ, y = hwy)) +
  geom_point(aes(color = class)) +
  geom_smooth()
# this is what it looks like with both plotted at the same time.
```