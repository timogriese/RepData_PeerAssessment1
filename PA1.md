# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data


```r
d<-read.csv(file = "activity.csv")
```

## Histogram of the total number of steps taken each day


```r
sumStepsByDate<-aggregate(d$steps, by = list(d$date), FUN = sum)
names(sumStepsByDate)<-c("date", "steps")
hist(sumStepsByDate$steps)
```

![](PA1_files/figure-html/unnamed-chunk-2-1.png)\

## Mean and median number of steps taken each day

```r
mean(sumStepsByDate$steps, na.rm = TRUE)
```

```
## [1] 10766.19
```

```r
median(sumStepsByDate$steps, na.rm = TRUE)
```

```
## [1] 10765
```

```r
meanStepsByDate<-aggregate(sumStepsByDate$steps, by = list(sumStepsByDate$date), FUN = mean)
names(meanStepsByDate)<-c("date", "steps")
hist(meanStepsByDate$steps)
```

![](PA1_files/figure-html/unnamed-chunk-3-1.png)\

```r
medianStepsByDate<-aggregate(d$steps, by = list(d$date), FUN = median)
names(medianStepsByDate)<-c("date", "steps")
hist(medianStepsByDate$steps)
```

![](PA1_files/figure-html/unnamed-chunk-3-2.png)\


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
