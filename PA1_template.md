# Reproducible Research: Peer Assessment 1




## Loading and preprocessing the data

```r
AMDdata<-read.csv(file="activity.csv")
```


```r
sumstepsperday<-tapply(AMDdata$steps,AMDdata$date,sum)
hist(sumstepsperday, main="Total steps per day", col="yellow",breaks = 10)
```

![](PA1_template_files/figure-html/histogram-1.png)<!-- -->

## What is mean total number of steps taken per day?

```r
meanstepsperday<-mean(sumstepsperday, na.rm=TRUE)
medianstepsperday<-median(sumstepsperday, na.rm=TRUE)
```
The mean is 10766.19, and the median is 10765

## What is the average daily activity pattern?

```r
meanstepsinterval<-tapply(AMDdata$steps,AMDdata$interval,mean, na.rm=TRUE, simplify = TRUE)
interval<-as.numeric(names(meanstepsinterval))
meanstep<-as.data.frame(as.matrix(meanstepsinterval))
plot(interval,meanstep$V1, type="l", xlab="interval, 5min", ylab="Average steps", col="blue")
```

![](PA1_template_files/figure-html/activity pattern-1.png)<!-- -->

## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?


## need to be commited at least once
