# Reproducible Research: Peer Assessment 1
## Requirements for project

```r
require(dplyr)
```

```
## Loading required package: dplyr
## 
## Attaching package: 'dplyr'
## 
## The following object is masked from 'package:stats':
## 
##     filter
## 
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

```r
require(ggplot2)
```

```
## Loading required package: ggplot2
```
## Loading and preprocessing the data


```r
unzip("activity.zip",files = "activity.csv")
activities <- read.csv("activity.csv",header = TRUE, colClasses = c("numeric","character","numeric"))
activities$date <- as.Date(activities$date)
```

## What is mean total number of steps taken per day?

Histogram of steps per day:

```r
groupedActivities <- group_by(activities, date)
stepsPerDay <- summarise(groupedActivities, stepsPerDay = sum(steps,na.rm = TRUE))
qplot(stepsPerDay$stepsPerDay, binwidth=1500)
```

![](PA1_template_files/figure-html/unnamed-chunk-3-1.png) 

Mean and median of total steps per day:

```r
mean(stepsPerDay$stepsPerDay)
```

```
## [1] 9354.23
```

```r
median(stepsPerDay$stepsPerDay)
```

```
## [1] 10395
```


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
