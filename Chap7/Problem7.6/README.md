# Chapter 7 Problem 7.6 
## Implementation of Averaged One-Dependent Estimator (AODE) of Semi-Naïve Bayes Classifier

This repository contains my personal notes and codes for problem 7.6 in Chapter 7. An AODE is implemented. The main steps are as follows:

1. Prior probabiltiy compution
2. Conditional probability compution
3. Computing the sum of cumulative product of probability for each class
4. Return the class with the largest Probability

## Probability Function
### 1. Categorical Variables
In particular, the prior and conditional probability of two categorical variables, <a href="https://www.codecogs.com/eqnedit.php?latex=x_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{i}" title="x_{i}" /></a> and <a href="https://www.codecogs.com/eqnedit.php?latex=x_{j}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{j}" title="x_{j}" /></a> are given by the following functions:

- The prior probability <a href="https://www.codecogs.com/eqnedit.php?latex=\hat{P}&space;(c,x_{i})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\hat{P}&space;(c,x_{i})" title="\hat{P} (c,x_{i})" /></a> can be estimated as equation 1:
<p align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=\hat{P}&space;(c,x_{i})&space;=&space;\frac{|D_{c,&space;x_{i}}|&space;&plus;&space;1}{|D|&plus;&space;N_{i}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\hat{P}&space;(c,x_{i})&space;=&space;\frac{|D_{c,&space;x_{i}}|&space;&plus;&space;1}{|D|&plus;&space;N_{i}}" title="\hat{P} (c,x_{i}) = \frac{|D_{c, x_{i}}| + 1}{|D|+ N_{i}}" /></a>
</p>

- The conditional probability <a href="https://www.codecogs.com/eqnedit.php?latex=\hat{P}&space;(x_{j}|c,&space;x_{i})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\hat{P}&space;(x_{j}|c,&space;x_{i})" title="\hat{P} (x_{j}|c, x_{i})" /></a> can be estimated as equation 2:

<p align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=\hat{P}&space;(x_{j}|c,&space;x_{i})&space;=&space;\frac{|D_{c,x_{i},&space;x_{j}}|&plus;1}{|D_{c,x_{i}}|&space;&plus;&space;N_{j}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\hat{P}&space;(x_{j}|c,&space;x_{i})&space;=&space;\frac{|D_{c,x_{i},&space;x_{j}}|&plus;1}{|D_{c,x_{i}}|&space;&plus;&space;N_{j}}" title="\hat{P} (x_{j}|c, x_{i}) = \frac{|D_{c,x_{i}, x_{j}}|+1}{|D_{c,x_{i}}| + N_{j}}" /></a>
</p>


### 2. Continuous Variable
Based on these functions, we are going to introduce the probability function of continuous variables. 

Firstly, when <a href="https://www.codecogs.com/eqnedit.php?latex=x_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{i}" title="x_{i}" /></a> is continuous, assume <a href="https://www.codecogs.com/eqnedit.php?latex=x_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{i}" title="x_{i}" /></a> follows a Gaussian Distribution, then we have the conditional probability <a href="https://www.codecogs.com/eqnedit.php?latex=\hat{P}&space;(c,x_{i})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\hat{P}&space;(c,x_{i})" title="\hat{P} (c,x_{i})" /></a> define as equation 3:
<p align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=\hat{P}&space;(x_{i}|c)&space;=&space;\frac{1}{{\sigma&space;\sqrt&space;{2\pi&space;}&space;}}e^{{{&space;-&space;\left(&space;{x_{i}&space;-&space;\mu&space;}&space;\right)^2&space;}&space;\mathord{\left/&space;{\vphantom&space;{{&space;-&space;\left(&space;{x&space;-&space;\mu&space;}&space;\right)^2&space;}&space;{2\sigma&space;^2&space;}}}&space;\right.&space;\kern-\nulldelimiterspace}&space;{2\sigma&space;^2&space;}}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\hat{P}&space;(x_{i}|c)&space;=&space;\frac{1}{{\sigma&space;\sqrt&space;{2\pi&space;}&space;}}e^{{{&space;-&space;\left(&space;{x_{i}&space;-&space;\mu&space;}&space;\right)^2&space;}&space;\mathord{\left/&space;{\vphantom&space;{{&space;-&space;\left(&space;{x&space;-&space;\mu&space;}&space;\right)^2&space;}&space;{2\sigma&space;^2&space;}}}&space;\right.&space;\kern-\nulldelimiterspace}&space;{2\sigma&space;^2&space;}}}" title="\hat{P} (x_{i}|c) = \frac{1}{{\sigma \sqrt {2\pi } }}e^{{{ - \left( {x_{i} - \mu } \right)^2 } \mathord{\left/ {\vphantom {{ - \left( {x - \mu } \right)^2 } {2\sigma ^2 }}} \right. \kern-\nulldelimiterspace} {2\sigma ^2 }}}" /></a>

</p>

with <a href="https://www.codecogs.com/eqnedit.php?latex=\mu" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\mu" title="\mu" /></a> and <a href="https://www.codecogs.com/eqnedit.php?latex=\sigma" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sigma" title="\sigma" /></a> of <a href="https://www.codecogs.com/eqnedit.php?latex=x_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{i}" title="x_{i}" /></a> calculated on the sub-data which is classified as class, c.

Secondly, based on conditional probability formula, we have equation 4:

<p align="center">
  <a href="https://www.codecogs.com/eqnedit.php?latex=P(x_{j}&space;|&space;c,&space;x_{i})&space;=&space;\frac{P(x_{i},&space;x_{j}&space;|&space;c)}{P(x_{i}&space;|&space;c)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(x_{j}&space;|&space;c,&space;x_{i})&space;=&space;\frac{P(x_{i},&space;x_{j}&space;|&space;c)}{P(x_{i}&space;|&space;c)}" title="P(x_{j} | c, x_{i}) = \frac{P(x_{i}, x_{j} | c)}{P(x_{i} | c)}" /></a>
</p>

Then when both <a href="https://www.codecogs.com/eqnedit.php?latex=x_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{i}" title="x_{i}" /></a> and <a href="https://www.codecogs.com/eqnedit.php?latex=x_{j}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{j}" title="x_{j}" /></a> are continous variables, we could use equation 4 to solve the conditional probability <a href="https://www.codecogs.com/eqnedit.php?latex=\hat{P}&space;(x_{j}|c,&space;x_{i})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\hat{P}&space;(x_{j}|c,&space;x_{i})" title="\hat{P} (x_{j}|c, x_{i})" /></a>.

<p align="center">
  <a href="https://www.codecogs.com/eqnedit.php?latex=P(x_{j}&space;|&space;c,&space;x_{i})&space;=&space;\frac{P(x_{i},&space;x_{j}&space;|&space;c)}{P(x_{i}&space;|&space;c)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(x_{j}&space;|&space;c,&space;x_{i})&space;=&space;\frac{P(x_{i},&space;x_{j}&space;|&space;c)}{P(x_{i}&space;|&space;c)}" title="P(x_{j} | c, x_{i}) = \frac{P(x_{i}, x_{j} | c)}{P(x_{i} | c)}" /></a>
  
<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;(x_{i},&space;x_{j})&space;|&space;c)=&space;\frac{\exp\left(-\frac&space;1&space;2&space;({\mathbf&space;x}-{\boldsymbol\mu})^\mathrm{T}{\boldsymbol\Sigma}^{-1}({\mathbf&space;x}-{\boldsymbol\mu})\right)}{\sqrt{(2\pi)^k|\boldsymbol\Sigma|}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;(x_{i},&space;x_{j})&space;|&space;c)=&space;\frac{\exp\left(-\frac&space;1&space;2&space;({\mathbf&space;x}-{\boldsymbol\mu})^\mathrm{T}{\boldsymbol\Sigma}^{-1}({\mathbf&space;x}-{\boldsymbol\mu})\right)}{\sqrt{(2\pi)^k|\boldsymbol\Sigma|}}" title="P(X = (x_{i}, x_{j}) | c)= \frac{\exp\left(-\frac 1 2 ({\mathbf x}-{\boldsymbol\mu})^\mathrm{T}{\boldsymbol\Sigma}^{-1}({\mathbf x}-{\boldsymbol\mu})\right)}{\sqrt{(2\pi)^k|\boldsymbol\Sigma|}}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=\hat{P}&space;(x_{i}|c)&space;=&space;\frac{1}{{\sigma&space;\sqrt&space;{2\pi&space;}&space;}}e^{{{&space;-&space;\left(&space;{x_{i}&space;-&space;\mu&space;}&space;\right)^2&space;}&space;\mathord{\left/&space;{\vphantom&space;{{&space;-&space;\left(&space;{x&space;-&space;\mu&space;}&space;\right)^2&space;}&space;{2\sigma&space;^2&space;}}}&space;\right.&space;\kern-\nulldelimiterspace}&space;{2\sigma&space;^2&space;}}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\hat{P}&space;(x_{i}|c)&space;=&space;\frac{1}{{\sigma&space;\sqrt&space;{2\pi&space;}&space;}}e^{{{&space;-&space;\left(&space;{x_{i}&space;-&space;\mu&space;}&space;\right)^2&space;}&space;\mathord{\left/&space;{\vphantom&space;{{&space;-&space;\left(&space;{x&space;-&space;\mu&space;}&space;\right)^2&space;}&space;{2\sigma&space;^2&space;}}}&space;\right.&space;\kern-\nulldelimiterspace}&space;{2\sigma&space;^2&space;}}}" title="\hat{P} (x_{i}|c) = \frac{1}{{\sigma \sqrt {2\pi } }}e^{{{ - \left( {x_{i} - \mu } \right)^2 } \mathord{\left/ {\vphantom {{ - \left( {x - \mu } \right)^2 } {2\sigma ^2 }}} \right. \kern-\nulldelimiterspace} {2\sigma ^2 }}}" /></a>

</p>


<a href="https://www.codecogs.com/eqnedit.php?latex=x_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{i}" title="x_{i}" /></a> Categorical Variable and <a href="https://www.codecogs.com/eqnedit.php?latex=x_{j}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{j}" title="x_{j}" /></a> Continuous Variable



