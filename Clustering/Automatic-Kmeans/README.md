# Chapter 9 Problem 9.10
## Implementation of K-Means with Automatically K Selection

This repository contains my personal notes and codes for problem 9.10 in Chapter 9. A K-Means algorithm with automatically k selection for classification problem is implemented. The main steps are as follows:

1. Iterating through the range of possible n and calculating the sum of distance from each point to its centroid 
2. Selecting the the turning point, n, whose slope changing a lot, which is defined as 

<p align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=\frac{dist(k=n-1)&space;-&space;dist(k=n)}{dist(k=n)-dist(k=n&plus;1)}&space;>&space;threshold" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{dist(k=n-1)&space;-&space;dist(k=n)}{dist(k=n)-dist(k=n&plus;1)}&space;>&space;threshold" title="\frac{dist(k=n-1) - dist(k=n)}{dist(k=n)-dist(k=n+1)} > threshold" /></a>
</p>

For instance, in the following graph, the turning point is k = 3. 


<br />
<img src="https://github.com/Hatchin/Machine-Learning-Zhou_Zhihua/blob/master/Clustering/Automatic-Kmeans/k-mean.png"> <br />




