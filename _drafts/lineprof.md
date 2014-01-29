---
layout: post
title: A lineprof example
---

Memory usage is an important aspect of using and developing for R. For a while, we have had the
possibility of doing memory profiling in R, but it has been hard to use. This was recently
revolutionized by Hadley Wickham's lineprof package.

What follows is my first attempt at using this package for memory profiling on one of my own R
packages. This is an edited transcript of that attempt, and it shows how I managed to improve the
memory usage in less than 2 hours, including reading the documentation of lineprof. In my opinion,
this is very good value for money.

lineprof installation
---------------------

I don't think lineprof is on CRAN.  You can get it from github using devtools

```r
install.packages("devtools")
library(devtools)
devtools::install_github("lineprof")
```

```r
library(lineprof)
library(minfiData)
data(RGsetEx)
prof <- lineprof(out <- preprocessRaw(RGsetEx))
prof

Reducing depth to 2 (from 49)
    time   alloc release  dups                                   ref
1  0.697  57.106   9.783     6           c("preprocessRaw", ".isRG")
2  0.593  52.868  17.123  1840 c("preprocessRaw", "getManifestInfo")
3  0.133   4.025   9.841   580          c("preprocessRaw", "matrix")
4  0.140   8.805   0.000   332                       "preprocessRaw"
5  0.001   0.307   0.000     0 c("preprocessRaw", "lazyLoadDBfetch")
6  0.118   8.993  11.672   172                       "preprocessRaw"
7  0.362  53.227  51.545 14811    c("preprocessRaw", "getProbeInfo")
8  0.120  11.345   7.343   306                       "preprocessRaw"
9  0.001   0.624   0.000     0               c("preprocessRaw", "$")
10 0.011   0.730   0.000    36                       "preprocessRaw"
11 0.858 319.958 242.030 16250             c("preprocessRaw", "new")
12 0.001   0.121   0.000    46  c("preprocessRaw", "packageVersion")
13 0.016   0.000   0.463   149                       "preprocessRaw"
                             src
1  preprocessRaw/.isRG          
2  preprocessRaw/getManifestInfo
3  preprocessRaw/matrix         
4  preprocessRaw                
5  preprocessRaw/lazyLoadDBfetch
6  preprocessRaw                
7  preprocessRaw/getProbeInfo   
8  preprocessRaw                
9  preprocessRaw/$              
10 preprocessRaw                
11 preprocessRaw/new            
12 preprocessRaw/packageVersion 
13 preprocessRaw                
```
