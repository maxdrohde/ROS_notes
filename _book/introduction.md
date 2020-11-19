# Overview


```r
library(tidyverse)
library(extrafont)
```



```r
# Figure 1.1

df <- read.table("~/ROS_notes/ROS-Examples-master/ElectionsEconomy/data/hibbs.dat", header=TRUE)

# Convert from percentage to decimal
df$growth <- df$growth / 100
df$vote <- df$vote / 100

df %>%
  ggplot(aes(x = growth, y = vote, label = year)) +
  geom_point(alpha = 0.5) +
  geom_text(nudge_y = -0.01, size=3.5) +
  stat_smooth(geom='line', alpha=0.5, se=TRUE, method='lm', color="steelblue") +
  stat_smooth(geom='ribbon', method='lm', alpha=0.2, fill="gray") +
  scale_y_continuous(labels = scales::percent_format(accuracy = 1), limits = c(0.35, 0.65)) +
  scale_x_continuous(labels = scales::percent_format(accuracy = 1)) +
  cowplot::theme_cowplot() +
  theme(text=element_text(size=12, family="Source Sans Pro"))+
  labs(
    title = "Economic growth predicts incumbent vote percentage",
    x = "Average recent growth in personal income",
    y = "Incumbent vote percentage",
    caption = "Data ranges from 1952 to 2012"
  )
```

<img src="introduction_files/figure-html/unnamed-chunk-2-1.png" width="672" />

