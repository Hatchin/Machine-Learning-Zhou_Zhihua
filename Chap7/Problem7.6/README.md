# Chapter 7 Problem 7.6 
## Implementation of Averaged One-Dependent Estimator (AODE) of Semi-Naïve Bayes Classifier

This repository contains my personal notes and codes for problem 7.6 in Chapter 7. An AODE is implemented. The main steps are as follows:

1. Prior probabiltiy compution
2. Conditional probability compution
3. Computing the sum of cumulative product of probability for each class
4. Return the class with the largest Probability

In particular, the prior and conditional probability of two categorical variables, $x_{i}$ and $x_{j}$ are given by the following functions:

- The prior probability of a class $\hat{P} (c,x_{i})$ can be estimated as
<a href="https://www.codecogs.com/eqnedit.php?latex=\hat{P}&space;(c,x_{i})&space;=&space;\frac{|D_{c,&space;x_{i}}|&space;&plus;&space;1}{|D|&plus;&space;N_{i}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\hat{P}&space;(c,x_{i})&space;=&space;\frac{|D_{c,&space;x_{i}}|&space;&plus;&space;1}{|D|&plus;&space;N_{i}}" title="\hat{P} (c,x_{i}) = \frac{|D_{c, x_{i}}| + 1}{|D|+ N_{i}}" /></a>

- The conditional probability $ \hat{P} (x_{j}|c, x_{i}) $ can be estimated as
$$ \hat{P} (x_{j}|c, x_{i}) = \frac{|D_{c,x_{i}, x_{j}}|+1}{|D_{c,x_{i}}| + N_{j}} $$

