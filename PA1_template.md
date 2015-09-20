# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data



```r
readData<-function() {
        
        ## unzip it
        unzip("./activity.zip", overwrite = T)
        ## return it in a dataframe
        activityDF<-read.csv("activity.csv",header=TRUE, na.strings = "NA")
         activityDF$date<-as.Date(activityDF$date)
        activityDF
}




activityDF<-readData()

sumSteps<-aggregate(steps ~ date, activityDF, sum)

meanSteps<-aggregate(steps ~ date, activityDF, mean)


  hist(sumSteps$steps,  ylab="days", col="red", xlim=c(1000,20000), xlab="mean steps per day", breaks=20)
```

![](PA1_template_files/figure-html/unnamed-chunk-1-1.png) 

## What is mean total number of steps taken per day?



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
