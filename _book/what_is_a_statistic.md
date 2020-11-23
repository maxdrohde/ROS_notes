# What is a Statistic?




```r
library(tidyverse)
library(extrafont)
```

## Simulating statistics of dice rolls


```r
# A function to roll `n` dice
roll <- function(n){
  sample(x = 1:6, size=n, replace=TRUE)
}

# Returns the nth order statistic of the sample
order_stat <- function(x, n){
  x <- sort(x)
  return(x[n])
}
```


```r
# Roll 5 dice 100,000 times
data <- map(1:1e5, ~roll(5))

# Look at first three rolls
data[1:3]
```

```
## [[1]]
## [1] 4 2 3 5 4
## 
## [[2]]
## [1] 2 6 4 2 3
## 
## [[3]]
## [1] 2 5 4 4 1
```


```r
# Generate various statistics for each roll
medians <- map_dbl(data, ~median(.x))
means <- map_dbl(data, ~mean(.x))
minimums <- map_dbl(data, ~min(.x))
maximums <- map_dbl(data, ~max(.x))
second_order_stat <- map_dbl(data, ~order_stat(x=.x, n=2))
ranges <- maximums - minimums
```


```r
df <- tibble(medians, means, minimums, maximums, second_order_stat, ranges)

df <- pivot_longer(df, cols = everything())
```

<div class="figure">
<img src="what_is_a_statistic_files/figure-html/unnamed-chunk-7-1.png" alt="Various order statistics for rolls of 5 standard dice. Frequencies were calculated using 100,000 simulations." width="100%" />
<p class="caption">(\#fig:unnamed-chunk-7)Various order statistics for rolls of 5 standard dice. Frequencies were calculated using 100,000 simulations.</p>
</div>

