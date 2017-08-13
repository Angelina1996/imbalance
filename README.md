
<!-- README.md is generated from README.Rmd. Please edit that file -->
imbalance
=========

[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](http://www.repostatus.org/badges/latest/wip.svg)](http://www.repostatus.org/#wip) [![Build Status](https://travis-ci.org/ncordon/imbalance.svg?branch=master)](https://travis-ci.org/ncordon/imbalance) [![minimal R version](https://img.shields.io/badge/R%3E%3D-3.4.1-6666ff.svg)](https://cran.r-project.org/) [![CRAN\_Status\_Badge](http://www.r-pkg.org/badges/version/imbalance)](https://cran.r-project.org/package=imbalance) [![packageversion](https://img.shields.io/badge/Package%20version-0.0.0.9000-orange.svg?style=flat-square)](https://github.com/ncordon/imbalance/commits/master)

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
library("imbalance")

data(iris0)
set.seed(12345)

rwoSamples <- rwo(iris0, numInstances = 100)
rwoBalanced <- rbind.data.frame(iris0, rwoSamples)
plotComparison(iris0, rwoBalanced, names(iris0), cols = 2, classAttr = "Class")
```

![](README-example-1.png)
