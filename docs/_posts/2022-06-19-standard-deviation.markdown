---
layout: post
title:  "STD dev"
date:   2022-06-19 15:52:21 +0200
use_math: true
categories: jekyll update
---
>Standard deviation is a measure of how spread out numbers are. 

The symbol is $\sigma$, the greek letter sigma.  

Its the square root of the variance:  
$$
\sigma = \sqrt{Variance}  \Rightarrow Variance = \sqrt{\sigma}
$$

To understand standard deviation, we need to understand variance
> Variance is the average of the _squared_ differences from the mean. Squared because it weighs outliers more heavily than data close to the mean. It also prevents negative differences to cancel out positive value (although this could be solved by taking the absolute value of the differences).

1. Calculate the _mean_ ($\mu$)  
2. For each number, subtract the mean and square the difference
3. Calculate the average of those squared differences

Standard deviation is the square root of Variance: 

$$ \sigma  = \sqrt{\frac{1}{N}\sum_{i=1}^{N}(x_{i} - \mu)^{2}} $$

Note that this is the formula for _population_ standard deviation, where all individuals are included in the population.
$\mu$ is the population mean.

# Sample Standard Deviation
Sometime the data available is only a __sample__ of the whole population. To compensate for this uncertainty, the formula is _slightly_ changed by dividing by $N-1$ instead of $N$

$$ \sigma  = \sqrt{ \frac{1}{N-1}\sum_{i=1}^{N}(x_{i} - \bar{x})^{2} } $$

$${\bar{x}}={\frac{1}{N}}\sum_{i=1}^{N}x_{i}$$

$\mu$ is calculated the same way as $\bar{x}$, but $\mu$ is the real mean assuming we have all the data, whereas $\bar{x}$ is our best guess given based on the samples available.
