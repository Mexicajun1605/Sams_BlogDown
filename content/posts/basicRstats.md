---
date: "2023-10-07"
tags:
- Statistics
- R
- Computers
- Mathematics
title: Basic Statistics with R
---

# How to perform basic Statistics with R 

This post is going to describe how to perform some basic statistical anlaysis with R. To do this you will first need to install R either using the command line on Linux(Debian and Ubuntu based) with the command below or by downloading from [CRAN](https://cran.r-project.org/mirrors.html). 

```
sudo apt -y install r-base
``` 
While an IDE like Rstudio will be useful, you should be able to follow along in the command line terminal. 

# Getting started 

Once you have R installed, open the command line on your computer. This will either be accessible on Windows by searching for the command prompt or on Linux by opening the terminal, a common shortcut being CTRL + ALT + t.  
Thankfully R contains some datasets built in. We are going to be using the cars dataset. To access and View this data, type in the following command. Note that R is case-sensitive.  

```
data(cars)
View(cars)
``` 

To view our dataset, lets use the head() command. This command will let you see the first ten observations of the data that you wish to see. Something that I think is worthy of note is that the thing you want to do to your data, usually precedes the data object, i.e. first head then cars. 

```
head(cars)
``` 

# The mean, median, mode, and more 

## The mean 

The mean is the sum of the observations divided by the number of observations. For example, if we have a vector(think of it as a list) of numbers as follows that we call list, then we know that the mean is 2 because 1+2+3 is 6 and there are three numbers. 6 divided by 3 is 2. Thus we have our mean. Thankfully in R, we do not have to go through all of these steps to get our mean; this would take a very long time with long datasets. Instead we just use the mean() function as below. 

```
x <- c(1, 2, 3) #In R we denote vectors with a c before the list in 
#parentheses. The <- assigns the list to x
mean(x)
``` 

To find out what the mean speed is in our cars dataset, lets use the same function. To denote a specific column in a dataset, we use the dataset name $ followed by the name of the variable.  

```
mean(cars$speed)
``` 

This should return 15.4. 

## Median 

Commonly confused with mean, the median is actually the middle observation in a set of observations when listed from smallest to largest or vice-versa. For example, in our cars dataset we have 50 observations. Since this number is even, and thus not having a true middle, we take the two middle numbers add them together then divide them by 2. In R, we can use the median function to find this. To find the median of speed we can use the code below.

```
median(cars$speed)
``` 

## Mode 

The mode is the most frequent value found within a dataset. Since multiples of the same observations can be observed within the same variables. An example of how the mode can be useful is finding the most common word in a text when using non-numeric data. 

To find the mode with R, there is unfortunately not a built-in function for that. However, since R is a fully fledged programming language, we have the ability to create our own functions. To find the mode, you can use the code below from [statology.com](https://www.statology.org/mode-in-r/). This should return 20. 

```
#Thanks to statology for providing this function
find_mode <- function(x) {
  u <- unique(x)
  tab <- tabulate(match(x, u))
  u[tab == max(tab)]
}
```

## Standard Deviation 

Standard Deviation refers to the most common deviation from the mean. For example, if the mean of cars$speed is 15.4 and most observations are close to 10.4 or 20.4 then the standard deviation is close to 5. 
If the standard deviation is low, then the majority of the data is close to the mean, otherwise if it is high, the data is widely spread out.  

To find this, R has a function. Running the code below should yield 5.287644. 

```
sd(cars$speed)
``` 

One more thing to note about the standard deviation is the 68-95-99% rule. In a normal distribution of data, meaning the data is shaped like a symmetric slope or bell, 68% of observations will be within one standard deviation, 95% within 2, and 99% within 3. If the data is not normal, then it is said to be skewed in the direction of the smaller end of the distribution. 
That sounds really complicated. Thankfully R has our back with built-in visualization functions. A histogram is a type of chart that plots bars similar to a bar chart but clustered together. It is a great way to view distribution. To use it, just use the hist() function. Lets take a look at some normally distributed data now using the code below. 


```r
#Here the rnorm function generates the normal distribution for us
#the first number represents the amount of observations while the 
#breaks argument in hist simply means how many line break points we
# want, i.e. the vertical lines between bars in the histogram. 
nd <- rnorm(10000, mean = 0, sd =1)
hist(nd, breaks = 50)
```

![](/images/basicRstats/normalDistro.png)

Although this graph does not mark the 1 and 3, we can see that 68% of the data here is between 1 and -1, 95% between 2 and -2, and 99% between 3 and -3. 

Now that we have the basic idea under our belts, lets check out what the distribution for our cars$speed looks like.


```r
hist(cars$speed)
```

![](/images/basicRstats/carSpeed.png)

Here we can see that the data for our cars$speed is slightly skewed to the left and not normal. 

## Minimum and Maximum 

This is probably the simplest of the basic stats to derive. The minimum is the smallest value while the maximum is the largest. To get these, we use the min() and max() functions respectively. They should yield a min of 4 and a max of 25. 

```
min(cars$speed)
max(cars$speed)
```

# Generating a summary of Statistics 

One neat thing about R is that when you are first exploring your data you can use a single function to get a lot these statistics all at once and even more. To do so, we just ask R for a summary like so. 

```
summary(cars$speed)
``` 
This generates the text below. 
```
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    4.0    12.0    15.0    15.4    19.0    25.0 
``` 
We now have our minimum, maximum, mean, and median. Additionally we have our 1st and 3rd quartiles. These are numbers that mark off the bottom 25% of our data and the top 75% of our data. For example, in the summary above, the bottom 25% of our speed observations were 12.0 or lower and the top 25% (because 100 -75 which is the third quartile) were 19.0 or higher. 

We can even visualize these stats on what we call a boxplot using the code below. 


```r
boxplot(cars$speed)
```

![](/images/basicRstats/boxSpeed.png)

In the boxplot, the dark line in the middle of the box is the median, the top and bottom edges of the box are the 1st and 3rd quartiles, and the high and low horizontal lines connected to the box represent the maximum and minimum values of the data (this will not always be the case though, sometimes they represent other things such as the value of 1.5 times the 1st and 3rd quartiles.). If there are any outliers in your data when making boxplots, they will show up as a symbol either above or below the further out lines (which is also why they are not always the max or min). 
# One more plot 

Finally, you may want to view how your observations compare to other observations in your data. We are going to finish off the meat of this post with a simple way of doing this. Since our cars dataset only has two observations of distance and speed, it is fairly simple to plot them out using the function below. 


```r
plot(cars)
```

![](/images/basicRstats/carsDist.png)

# Conclusion 
Well that's it for today's post. I hope that you learned something from this tutorial and that it can help you with your research. Using R is not only useful, but I also find that it is very rewarding, especially for those of us who are math challenged like me. If you find this stuff to be difficult, know that you are not alone and that you can accomplish whatever you set your mind to. 
