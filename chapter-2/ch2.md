R Notebook
================

### Exercise 2.1

Use R to compute the product of the first 10 integers:  
1 \* 2 \* 3 \* 4 \* 5 \* 6 \* 7 \* 8 \* 9 \* 10

``` r
print(1 * 2 * 3 * 4 * 5 * 6 * 7 * 8 * 9 * 10 )
```

    ## [1] 3628800

### Exercise 2.2 Do the following using R:

1.  Compute the sum 924+124 and assign the result to a variable named a.
2.  Compute a\*a

``` r
a <- 924+124
a * a
```

    ## [1] 1098304

### Exercise 2.3 Answer the following questions:

What happens if you use an invalid character in a variable name? Try
e.g., the following:

``` r
# net income <- income - taxes
# net-income <- income - taxes
# ca$h <- income - taxes
```

What happens if you put R code as a comment? For example,

``` r
income <- 100
taxes <- 20
net_income <- income - taxes
# gross_income <- net_income + taxes
```

What happens if you remove a line break and replace it by a semicolon ;?
For example,

``` r
income <- 200; taxes <- 30
```

What happens if you do two assignments on the same line? For example,

``` r
income2 <- taxes2 <- 100
```

### Exercise 2.4 Do the following:

Create two vectors, height and weight, containing the heights and
weights of five fictional people (i.e., just make up some numbers!).

Combine your two vectors into a data frame.

``` r
height <- c(1.8, 1.7, 1.75, 1.77, 1.78) # meter (m)
weight <- c(80, 70, 67, 65, 66) # Kg
```

### Exercise 2.5

Try creating a vector using x \<- 1:5. What happens? What happens if you
use 5:1 instead? How can you use this notation to create the vector  
(1,2,3,4,5,4,3,2,10)?

``` r
x <- 1:5
print(x)
```

    ## [1] 1 2 3 4 5

``` r
x <- 5:1 
print(x)
```

    ## [1] 5 4 3 2 1

``` r
print(1:10)
```

    ##  [1]  1  2  3  4  5  6  7  8  9 10

### Exercise 2.6

Using the data you created in Exercise 2.4, do the following:

Compute the mean height of the people.

``` r
mean(height)
```

    ## [1] 1.76

Compute the correlation between height and weight.

``` r
cor(height, weight)
```

    ## [1] 0.3224949

### Exercise 2.7 Do the following:

Read the documentation for the function `length.` What does it do? Apply
it to your `height` vector.

``` r
?length
length(height)
```

    ## [1] 5

Read the documentation for the function `sort`. What does it do? What
does the argument `decreasing` (the values of which can be either
`FALSE` or `TRUE`) do? Apply the function to your weight vector.

``` r
?sort
sort(weight, decreasing = TRUE)
```

    ## [1] 80 70 67 66 65

### Exercise 2.8 Compute the following:

1.  sqrt(pi)
2.  e^2 \* (log(4))

``` r
print(sqrt(pi))
```

    ## [1] 1.772454

``` r
print((exp(2))*(log(4)))
```

    ## [1] 10.24341

### Exercise 2.9

R will return non-numerical answers if you try to perform computations
where the answer is infinite or undefined. Try the following to see some
possible results:

Compute 1/0 Compute 0/0 Compute √−1

``` r
print(1/0)
```

    ## [1] Inf

``` r
print(0/0)
```

    ## [1] NaN

``` r
print(sqrt(-1))
```

    ## Warning in sqrt(-1): NaNs produced

    ## [1] NaN

### Exercise 2.10

Install the palmerpenguins package from CRAN. We’ll use it for many of
the exercises and examples that follow.

``` r
install.packages("palmerpenguins")
```

    ## Installing package into 'C:/Users/Ansh/AppData/Local/R/win-library/4.5'
    ## (as 'lib' is unspecified)

    ## package 'palmerpenguins' successfully unpacked and MD5 sums checked
    ## 
    ## The downloaded binary packages are in
    ##  C:\Users\Ansh\AppData\Local\Temp\RtmpU1kqYa\downloaded_packages

``` r
library(ggplot2)
```

    ## Warning: package 'ggplot2' was built under R version 4.5.2

### Exercise 2.11

Load the palmerpenguins package that you installed in Exercise 2.10,
using `library(palmerpenguins)`. In this exercise, we’ll study the
penguins dataset contained in said package. View the documentation for
the penguins data and read about its variables. Check the data
structures: how many observations and variables and what type of
variables (numeric, categorical, etc.) are there?

``` r
library(palmerpenguins)
```

    ## Warning: package 'palmerpenguins' was built under R version 4.5.2

    ## 
    ## Attaching package: 'palmerpenguins'

    ## The following objects are masked from 'package:datasets':
    ## 
    ##     penguins, penguins_raw

``` r
View(penguins)
?penguins
str(penguins)
```

    ## tibble [344 × 8] (S3: tbl_df/tbl/data.frame)
    ##  $ species          : Factor w/ 3 levels "Adelie","Chinstrap",..: 1 1 1 1 1 1 1 1 1 1 ...
    ##  $ island           : Factor w/ 3 levels "Biscoe","Dream",..: 3 3 3 3 3 3 3 3 3 3 ...
    ##  $ bill_length_mm   : num [1:344] 39.1 39.5 40.3 NA 36.7 39.3 38.9 39.2 34.1 42 ...
    ##  $ bill_depth_mm    : num [1:344] 18.7 17.4 18 NA 19.3 20.6 17.8 19.6 18.1 20.2 ...
    ##  $ flipper_length_mm: int [1:344] 181 186 195 NA 193 190 181 195 193 190 ...
    ##  $ body_mass_g      : int [1:344] 3750 3800 3250 NA 3450 3650 3625 4675 3475 4250 ...
    ##  $ sex              : Factor w/ 2 levels "female","male": 2 1 1 NA 1 2 1 2 NA NA ...
    ##  $ year             : int [1:344] 2007 2007 2007 2007 2007 2007 2007 2007 2007 2007 ...

Compute summary statistics (means, median, min, max, counts for
categorical variables). Are there any missing values?

``` r
summary(penguins)
```

    ##       species          island    bill_length_mm  bill_depth_mm  
    ##  Adelie   :152   Biscoe   :168   Min.   :32.10   Min.   :13.10  
    ##  Chinstrap: 68   Dream    :124   1st Qu.:39.23   1st Qu.:15.60  
    ##  Gentoo   :124   Torgersen: 52   Median :44.45   Median :17.30  
    ##                                  Mean   :43.92   Mean   :17.15  
    ##                                  3rd Qu.:48.50   3rd Qu.:18.70  
    ##                                  Max.   :59.60   Max.   :21.50  
    ##                                  NA's   :2       NA's   :2      
    ##  flipper_length_mm  body_mass_g       sex           year     
    ##  Min.   :172.0     Min.   :2700   female:165   Min.   :2007  
    ##  1st Qu.:190.0     1st Qu.:3550   male  :168   1st Qu.:2007  
    ##  Median :197.0     Median :4050   NA's  : 11   Median :2008  
    ##  Mean   :200.9     Mean   :4202                Mean   :2008  
    ##  3rd Qu.:213.0     3rd Qu.:4750                3rd Qu.:2009  
    ##  Max.   :231.0     Max.   :6300                Max.   :2009  
    ##  NA's   :2         NA's   :2

### Exercise 2.12

Create a `scatterplot` with total sleep time along the x-axis and time
awake along the y-axis (using the `msleep` data). What pattern do you
see? Can you explain it?

``` r
library(ggplot2)
ggplot(msleep, aes(sleep_total, awake)) +
  geom_point()
```

![](ch2_files/figure-gfm/unnamed-chunk-19-1.png)<!-- -->

### Exercise 2.13

Using the penguins data, do the following:

Create a scatterplot with bill length along the x-axis and flipper
length along the y-axis. Change the x-axis label to read “Bill length
(mm)” and the y-axis label to “Flipper length (mm)”. Use species to set
the colour of the points.

Try adding the argument alpha = 1 to geom_point, i.e., geom_point(alpha
= 1). Does anything happen? Try changing the 1 to 0.75 and 0.25 and see
how that affects the plot.

``` r
ggplot(penguins, aes(bill_length_mm, flipper_length_mm, colour = species)) +
  geom_point(alpha = 1) + 
  labs(x="Bill length (mm)", y="Flipper length (mm)")
```

    ## Warning: Removed 2 rows containing missing values or values outside the scale range
    ## (`geom_point()`).

![](ch2_files/figure-gfm/unnamed-chunk-20-1.png)<!-- -->

### Exercise 2.14

Similar to how you changed the colour of the points, you can also change
their size and shape. The arguments for this are called size and shape.

Change the scatterplot from Exercise 2.13 so that animals from different
islands are represented by different shapes.

Then change it so that the size of each point is determined by the body
mass, i.e., the variable body_mass_g.

``` r
ggplot(penguins, aes(bill_length_mm, flipper_length_mm, colour = species, shape = island, size = body_mass_g)) +
  geom_point(alpha = 0.5) + 
  labs(x="Bill length (mm)", y="Flipper length (mm)")
```

    ## Warning: Removed 2 rows containing missing values or values outside the scale range
    ## (`geom_point()`).

![](ch2_files/figure-gfm/unnamed-chunk-21-1.png)<!-- -->

### Exercise 2.15

Using the msleep data, create a plot of log-transformed body weight
versus log-transformed brain weight. Use total sleep time to set the
colours of the points. Change the text on the axes to something
informative.

``` r
ggplot(msleep, aes(bodywt, brainwt, colour = sleep_total)) + 
      geom_point(size=2.4) +
      labs( x= "log scale body weight",y = "log scale brain weight") +
      scale_x_log10() +
      scale_y_log10()
```

    ## Warning: Removed 27 rows containing missing values or values outside the scale range
    ## (`geom_point()`).

![](ch2_files/figure-gfm/unnamed-chunk-22-1.png)<!-- -->

### Exercise 2.16 Using the penguins data, do the following:

Create a scatterplot with bill_length_mm along the x-axis and
flipper_length_mm along the y-axis, facetted by species.

Read the documentation for facet_wrap (?facet_wrap). How can you change
the number of rows in the plot grid? Create the same plot as in part 1,
but with 2 rows.

``` r
ggplot(penguins, aes(bill_length_mm, flipper_length_mm)) +
  geom_point(size = 1.5) +
  labs(x="bill length (mm)", y="flipper length (nn)") +
  facet_wrap(~species, nrow =2)
```

    ## Warning: Removed 2 rows containing missing values or values outside the scale range
    ## (`geom_point()`).

![](ch2_files/figure-gfm/unnamed-chunk-23-1.png)<!-- -->

### Exercise 2.17

Using the penguins data, do the following: Create boxplots of bill
lengths, grouped by species. Read the documentation for `geom_boxplot.`
How can you change the colours of the boxes and their outlines? Add
`geom_jitter(size = 0.5, alpha = 0.25)`to the plot. What happens?

``` r
ggplot(penguins, aes(species, bill_length_mm)) +
  geom_boxplot(box.colour = "black", fill = "skyblue" ) +
  geom_jitter(size = 1, alpha = 0.5, colour = "#522363") 
```

    ## Warning: Removed 2 rows containing non-finite outside the scale range
    ## (`stat_boxplot()`).

    ## Warning: Removed 2 rows containing missing values or values outside the scale range
    ## (`geom_point()`).

![](ch2_files/figure-gfm/unnamed-chunk-24-1.png)<!-- -->
