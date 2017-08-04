
<!-- README.md is generated from README.Rmd. Please edit that file -->
imbalance
=========

`imbalance` provides a set of tools to work with imbalanced datasets: novel oversampling algorithms, filtering of instances and evaluation of synthetic instances.

Installation
------------

You can install imbalance from github with:

``` r
# install.packages("devtools")
devtools::install_github("ncordon/imbalance")
```

Examples
--------

Run `rwo` algorithm on `iris0` imbalanced dataset and plot a comparison between attributes.

``` r
library('imbalance')

data(iris0)
set.seed(12345)

rwoSamples <- rwo(iris0, numInstances = 100)
rwoBalanced <- rbind.data.frame(iris0, rwoSamples)
plotComparison(iris0, rwoBalanced, "Class", col=2, names(iris0))
```

![](README-example-1.png)

    #> [1] "Comparative grid plotted"
