---
title       : Data Product 
subtitle    : Galton's Height Data
author      : Claudio Seidi Takamiya
job         :
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction 
This work is based on Galton's Height Data.


* The Galton's Heigth Data can be found in HistData library
* There is a more detailed data inclunding child gender. The dataset is 
GaltonFamilies
* This work checks the influence of the child gender on its height.

The code below load the GaltonFamilies dataset.


```r
library(HistData)
data(GaltonFamilies)
```

--- .class #id 

## Exploratory Analysis


![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3.png) 

By splitting the dataset by gender and plotting their graphs, it is possible to conclude that the child gender has some correlation with its height.

---
## Considering child gender

The application can show the difference between male and female height.

```r
fit <- expand.grid(list(x=68.46, y=63))
male <- predict(gfMale.loess, newdata=fit) 
female <- predict(gfFemale.loess, newdata=fit)
```

```r
male
```

```
##          y
## x          y=63
##   x=68.46 68.61
```

```r
female
```

```
##          y
## x         y=63
##   x=68.46 63.5
```


---
## Conclusion
The child gender is a important estimator and can improve the prediction. In this application the LOESS method is used. However we don't mean this is the better algorithm for this problem.

### Thank you!



