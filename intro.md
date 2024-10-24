# R Code for Introducing the programming language

This document explains the basics of the R programming language and is an introduction for the language.

## 1. Clear Existing Variables and Outputs

First, we clear existing variables from memory to ensure a clean execution of the code.

```r
rm(list = ls())  # Clear out the variables from memory.
```

If you want to remove all previous plots and clear the console, run the following two lines:

```r
graphics.off()  # Clear all plots from previous work.
cat("\014")  # Clear the console.
```

## 2. Install and Load Necessary Libraries

We check if the `tidyverse`, `ggplot2`, and `reshape2` libraries are installed. If they aren't, we install them and then load them.

```r
if(!require('tidyverse')) {
  install.packages('tidyverse')  # Install tidyverse if not already installed.
  library('tidyverse')  # Load the tidyverse library.
}

if(!require('ggplot2')) {
  install.packages('ggplot2')  # Install ggplot2 if not already installed.
  library('ggplot2')  # Load the ggplot2 library.
}
```

## 2. How to Assign/Print Variables

```r
name <- "John Doe" # Assigning John Doe to name
print(name) # Printing John Doe

num1 <- 5 # Assigning 5 to num1
num2 <- 10 # Assigning 5 to num2
print(num1 + num2) # Prints out the value of 15
```

## 4. Using built in functions in R

```r
numbers <- c(10, 20, 30, 40) # Assign numbers to numbers
average <- mean(numbers) # Assign the average of the numbers to average
print(average) # Print the average

numbers <- c(3, 9, 1, 5, 12) # Assign the numbers to numbers
maximum <- max(numbers) # Assign the maximum number to maximum
minimum <- min(numbers) # Assign the minimum number to minimum
print(maximum) # Print the max
print(minimum) # Print the min
```

## 4. Plotting things with ggplot

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