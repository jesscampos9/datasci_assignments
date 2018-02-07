---
title: "Programming Assignment 2"
author: "Michele Goldin"
date: "1/30/2018"
output: 
  html_document: 
    highlight: kate
    keep_md: yes
    theme: united
---

## Plot 1


```r
library(languageR)
library(tidyverse)
```

```
## -- Attaching packages ---------------------------------- tidyverse 1.2.1 --
```

```
## <U+221A> ggplot2 2.2.1.9000     <U+221A> purrr   0.2.4     
## <U+221A> tibble  1.4.2          <U+221A> dplyr   0.7.4     
## <U+221A> tidyr   0.8.0          <U+221A> stringr 1.2.0     
## <U+221A> readr   1.1.1          <U+221A> forcats 0.2.0
```

```
## -- Conflicts ------------------------------------- tidyverse_conflicts() --
## x dplyr::filter() masks stats::filter()
## x dplyr::lag()    masks stats::lag()
```

```r
beginningReaders %>%
  select(., LogFrequency, Word) %>%
  ggplot(., aes(x = as.factor(Word), y = LogFrequency)) +
  geom_point()+
  labs(x="Word", y = "Log Frequency", title = "My Beginning Readers Scatterplot")
```

![](pa2_files/figure-html/unnamed-chunk-1-1.png)<!-- -->

```r
caption = "Log Frequency as a function of Word"
```

## Plot2


```r
english %>%
  ggplot(., aes(x = as.factor(AgeSubject), y = as.factor(Frication), color = VerbFrequency)) +
  geom_boxplot() +
  labs(x="Age", y = "Frication", title = "My English Boxplot")
```

![](pa2_files/figure-html/unnamed-chunk-2-1.png)<!-- -->

```r
caption = "My Boxplot"
```


##P lot3


```r
danish %>%
ggplot(., aes(x = as.factor(Subject), y = LogRT)) +
  stat_summary(fun.data = mean_cl_boot, geom = 'pointrange') + 
  facet_grid(. ~ Sex) +
  labs(x="Participants", y = "Reading Times", title = "My Danish Plot")
```

![](pa2_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

```r
caption = "Reading Times distributed by Sex"
```
