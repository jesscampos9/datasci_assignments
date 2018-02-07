---
title: "Programming Assignment 2"
author: "Dine Mamadou"
date: "2/6/2018"
output: 
  html_document:
    highlight: kate
    keep_md: yes
    theme: united
---


```r
library(tidyverse)
```

```
## ── Attaching packages ────────────────────────────── tidyverse 1.2.1 ──
```

```
## ✔ ggplot2 2.2.1     ✔ purrr   0.2.4
## ✔ tibble  1.3.4     ✔ dplyr   0.7.4
## ✔ tidyr   0.7.2     ✔ stringr 1.2.0
## ✔ readr   1.1.1     ✔ forcats 0.2.0
```

```
## ── Conflicts ───────────────────────────────── tidyverse_conflicts() ──
## ✖ dplyr::filter() masks stats::filter()
## ✖ dplyr::lag()    masks stats::lag()
```

```r
library(languageR)

english %>%
  ggplot(mapping =  aes(x = ConffV, y = ConffN), color = ConffN) +
  geom_point() +
  geom_smooth(se = TRUE)
```

```
## `geom_smooth()` using method = 'gam'
```

![](pa.2_files/figure-html/setup-1.png)<!-- -->

```r
beginningReaders %>%
  select(., Subject, LogRT) %>%
  ggplot(., aes(x = Subject, y = LogRT, fill = Subject)) +
  geom_boxplot()
```

![](pa.2_files/figure-html/setup-2.png)<!-- -->

```r
dativeSimplified %>%
  ggplot(., aes(x = AnimacyOfTheme, y = LengthOfTheme, color = AnimacyOfRec)) +
    geom_boxplot() +
    facet_grid(. ~ AnimacyOfRec) +
    geom_boxplot()+
    stat_summary(fun.data = mean_cl_boot) 
```

```
## Warning: Removed 1 rows containing missing values (geom_pointrange).
```

![](pa.2_files/figure-html/setup-3.png)<!-- -->

