Homework 1, Onyeka Isamah
================

# Attaching Tidyverse

``` r
library (tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.4     ✓ dplyr   1.0.7
    ## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
    ## ✓ readr   2.0.1     ✓ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

# Problem 1:

Creating a data frame using Tibble

    ## # A tibble: 10 × 4
    ##    vec_numeric vec_char vec_logical vec_factor
    ##          <dbl> <chr>    <chr>       <fct>     
    ##  1      -0.133 Wendy    TRUE        work      
    ##  2      -0.618 Kevin    TRUE        home      
    ##  3       1.67  Fred     TRUE        mobile    
    ##  4       1.90  Jeff     FALSE       work      
    ##  5       0.482 Leslie   TRUE        home      
    ##  6       0.726 Jen      TRUE        mobile    
    ##  7      -1.24  Michelle TRUE        work      
    ##  8       2.59  Emily    FALSE       home      
    ##  9       0.133 Jake     TRUE        mobile    
    ## 10       0.903 Sam      TRUE        home

## Taking the mean using the pull function

``` r
mean(pull (homework1_df, var = vec_numeric))
```

    ## [1] 0.6418024

``` r
mean(pull(homework1_df, var = vec_char))
```

    ## Warning in mean.default(pull(homework1_df, var = vec_char)): argument is not
    ## numeric or logical: returning NA

    ## [1] NA

``` r
mean(pull(homework1_df, var = vec_logical))
```

    ## Warning in mean.default(pull(homework1_df, var = vec_logical)): argument is not
    ## numeric or logical: returning NA

    ## [1] NA

``` r
mean(pull(homework1_df, var = vec_factor))
```

    ## Warning in mean.default(pull(homework1_df, var = vec_factor)): argument is not
    ## numeric or logical: returning NA

    ## [1] NA

## 

Taking the mean for the numeric variable in the data fram worked, but
taking the mean for the logical, character, and factor did not work.

# Using the as.numeric function to convert variable

I believe that the as.numeric function worked for vec\_factor because
this variable has a has 3 different “levels”. The numbers assigned are
now coded as 1,2, or 3.

When trying to convert vec\_char and vec\_logistical, I get a warning
message that says “NAs introduced by coercion”. \#

``` r
x <- as.numeric(pull(homework1_df, vec_factor))
mean(x)

y <- as.numeric(pull(homework1_df, vec_char))
mean(y)

z <- as.numeric(pull(homework1_df, vec_logical))
mean(z)
```
