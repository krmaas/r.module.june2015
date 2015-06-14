First try
========================================================
author: 
date: 

=======================================================
incremental: true
Create a project for this class

> File -> New Project

Choose working directory and name your project

Are you where you think you should be?

```r
getwd()
```

```
[1] "C:/data/R_module/r.module.june2015.1"
```

File names are relative in R, if you move your .Rproj file but none of the rest of the files your project won't function

Let's make a little practice dataset
=======================================================
incremental: true

```r
a <- 2
b <- -3
sigSq <- 0.5
x <- runif(40)  # this is R uniform, a function in base R
y <- a + b * x + rnorm(40, sd = sqrt(sigSq))
(avgX <- mean(x)) # () around the entire line says create avgX and print it
```

```
[1] 0.4465962
```

```r
write(avgX, file="avgX.txt")
```

First plot
=======================================================


```r
plot(x, y)
```

![plot of chunk unnamed-chunk-4](first.data-figure/unnamed-chunk-4-1.png) 

========================


```r
plot(x, y)
abline(a, b, col="purple")
```

![plot of chunk unnamed-chunk-5](first.data-figure/unnamed-chunk-5-1.png) 

===============


```r
dev.print(pdf, "practiceLine.pdf")
```

Finding help (part 1)
=======================================================
incremental: true
 `?plot`

 `?abline`

First script
=======================================================
incremental: true
* If you happy with how that plot looks (you can change lots of aspects but we won't right now), save the commands as a script.
    + Go into `History`
    + Highlight the lines you want
    + Click `To Source`
    + Save this as practiceLine.R
* Write yourself (or others) comments to explain what's going on by typing `#` 

Test your first script
=======================================================
incremental: true
* Clear out your workspace
    + `rm(list=ls())
    + and/or restart R (Session -> restart R)
* Open your project
* Execute your practiceLine.R script
* Did you recreate everything?

Importing data
=======================================================
incremental: true
* Download [this](http://www.stat.ubc.ca/~jenny/notOcto/STAT545A/examples/gapminder/data/gapminderDataFiveYear.txt) test dataset
* Import into your project

```r
gDat <- read.delim(file="gapminder.5year.txt") #read.delim is a special case of read.table, there are many of these and they can make you life much easier.  Read the read.table help
```
* You can also read the file in directly from the website but this only works with very carefully curated files

```r
gDat <- read.table(file="http://www.stat.ubc.ca/~jenny/notOcto/STAT545A/examples/gapminder/data/gapminderDataFiveYear.txt", fill=T)
```
* What kid of object is gDat?

Readings for Tomorrow
======================================================

[Tidy Data, Wickham 2014](http://www.jstatsoft.org/v59/i10/paper)

[Data sharing, White, et.al. 2013](http://library.queensu.ca/ojs/index.php/IEE/article/view/4608/4898)



