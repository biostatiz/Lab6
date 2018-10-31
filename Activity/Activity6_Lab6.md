Activity Six-Lab6
================
Taehoon Ha

-   [Question1](#question1)
-   [Question2](#question2)

### Question1

Create a function that calculates the sum of cubes of positive integers from 1 to *n* for a given value of *n*:

<p align="center">
<img src = 'https://ws2.sinaimg.cn/large/006tNbRwly1fwruwfxockj301r01w3ya.jpg'>
</p>
Your function should return two values: *n* and the sum.

``` r
sum.cube <- function(n) {
    num <- n
    sum.vec <- c()
    
    for (i in 1:n) {
        sum.vec[i] <- i * i * i
    }
    paste0("n is ", num, ", and the sum is ", sum(sum.vec), ".")
}

sum.cube(5)
```

    ## [1] "n is 5, and the sum is 225."

### Question2

Create a function that computes a binomial coefficient:

<p align="center">
<img src = 'https://ws1.sinaimg.cn/large/006tNbRwly1fwruvsl619j301g01igld.jpg'>
</p>
Please note: built-in functions **choose** and **factorial** are not allowed.

``` r
binom.coef <- function(n, k) {
    if (n < 0 | k < 0) {warning("The input should be greater or equal to zero.")}
    else if (n == k) {return(1)}
    else if (n < k) {return(0)}
    else {
        x <- 1:n
        a <- 1
        
        for (i in 1:n) {
        a <- a * x[i]
        } 
        
        y <- 1:k
        b <- 1
        
        for (i in 1:k) {
        b <- b * y[i]
        } 
        
        d <- n - k
        z <- 1:d
        c <- 1
        
        for (i in 1:d) {
        c <- c * z[i]
        }
        
        e <- a / (b * c)
        return(e)
    }
}

# Test Sets
binom.coef(0, 0) == choose(0, 0)
```

    ## [1] TRUE

``` r
binom.coef(1, 1) == choose(1, 1)
```

    ## [1] TRUE

``` r
binom.coef(5, 2) == choose(5, 2)
```

    ## [1] TRUE

``` r
binom.coef(7, 3) == binom.coef(7, 4)
```

    ## [1] TRUE

``` r
binom.coef(8, 3) == choose(8, 3)
```

    ## [1] TRUE
