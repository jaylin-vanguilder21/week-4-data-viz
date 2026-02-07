# Visualize Data
Jaylin Van Guilder

Try your code again

## Your Turn 0

Add a setup chunk that loads the tidyverse packages.

``` r
head(mpg)
```

    # A tibble: 6 × 11
      manufacturer model displ  year   cyl trans      drv     cty   hwy fl    class 
      <chr>        <chr> <dbl> <int> <int> <chr>      <chr> <int> <int> <chr> <chr> 
    1 audi         a4      1.8  1999     4 auto(l5)   f        18    29 p     compa…
    2 audi         a4      1.8  1999     4 manual(m5) f        21    29 p     compa…
    3 audi         a4      2    2008     4 manual(m6) f        20    31 p     compa…
    4 audi         a4      2    2008     4 auto(av)   f        21    30 p     compa…
    5 audi         a4      2.8  1999     6 auto(l5)   f        16    26 p     compa…
    6 audi         a4      2.8  1999     6 manual(m5) f        18    26 p     compa…

## Your Turn 1

Run the code on the slide to make a graph. Pay strict attention to
spelling, capitalization, and parentheses!

``` r
ggplot(data=mpg) +
  geom_point(mapping = aes(x = displ, y = hwy))
```

![](week-4-visualize-exercises_files/figure-commonmark/Creating%20ggplot%20graph-1.png)

``` r
# Don't need to always put 'mapping =' when doing the code, R will understand.
```

## Your Turn 2

Replace this scatterplot with one that draws boxplots. Use the
cheatsheet. Try your best guess.

``` r
ggplot(data = mpg) +
  geom_boxplot(mapping = aes(x = class, y = hwy))
```

![](week-4-visualize-exercises_files/figure-commonmark/ggplot%20boxplot-1.png)

## Your Turn 3

Make a histogram of the `hwy` variable from `mpg`. Hint: do not supply a
y variable.

``` r
ggplot(data = mpg) +
  geom_histogram(mapping = aes(x = hwy))
```

    `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](week-4-visualize-exercises_files/figure-commonmark/ggplot2%20Histogram-1.png)

## Your Turn 4

Use the help page for `geom_histogram` to make the bins 2 units wide.

``` r
ggplot(data = mpg) +
  geom_histogram(binwidth = 2, mapping = aes(x = hwy))
```

![](week-4-visualize-exercises_files/figure-commonmark/changing%20bin%20units-1.png)

## Your Turn 5

Add `color`, `size`, `alpha`, and `shape` aesthetics to your graph.
Experiment.

``` r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy), color = 3, size = 4, alpha = 0.5, shape = 2)
```

![](week-4-visualize-exercises_files/figure-commonmark/Adding%20color,%20size,%20alpha%20and%20shape%20to%20hist.-1.png)

## Help Me

What do `facet_grid()` and `facet_wrap()` do? (run the code, interpret,
convince your group)

``` r
# Makes a plot that the commands below will modify
q <- ggplot(mpg) + geom_point(aes(x = displ, y = hwy))

q + facet_grid(. ~ cyl)
```

![](week-4-visualize-exercises_files/figure-commonmark/Difference%20between%20facet%20grid%20and%20wrap-1.png)

``` r
q + facet_grid(drv ~ .)
```

![](week-4-visualize-exercises_files/figure-commonmark/Difference%20between%20facet%20grid%20and%20wrap-2.png)

``` r
q + facet_grid(drv ~ cyl)
```

![](week-4-visualize-exercises_files/figure-commonmark/Difference%20between%20facet%20grid%20and%20wrap-3.png)

``` r
q + facet_wrap(~ class)
```

![](week-4-visualize-exercises_files/figure-commonmark/Difference%20between%20facet%20grid%20and%20wrap-4.png)

> facet_grid forms a matrix of panels defined by row and column whereas
> facet_wrap wraps a 1d sequence of panels into 2d making a better use
> of screen space than facet_grid because most displays are mainly
> rectangular.

## Your Turn 6

Make a bar chart `class` colored by `class`. Use the help page for
`geom_bar` to choose a “color” aesthetic for class.

``` r
ggplot(data = mpg) +
  geom_bar(mapping = aes(x = class), color = 5)
```

![](week-4-visualize-exercises_files/figure-commonmark/Bar%20Chart-1.png)

## Quiz

What will this code do?

``` r
ggplot(mpg) + 
  geom_point(aes(displ, hwy)) +
  geom_smooth(aes(displ, hwy)) 
```

    `geom_smooth()` using method = 'loess' and formula = 'y ~ x'

![](week-4-visualize-exercises_files/figure-commonmark/unnamed-chunk-11-1.png)

``` r
#  ggsave("example.jpg")
```

> This code will make it easier to see the pattern in the scatterplot,
> the specific code to show this is the ‘geom_smooth()’ code.

------------------------------------------------------------------------

# Take aways

You can use this starter code template to make thousands of graphs with
**ggplot2**.

``` r
ggplot(data = <DATA>) +
  <GEOM_FUNCTION>(mapping = aes(<MAPPINGS>))
```
