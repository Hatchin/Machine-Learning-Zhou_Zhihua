# Chapter 4 Problem 4.7 
## Implementation of Decision Tree with Non-Recursive Approach

This repository contains my personal notes and codes for Problem 4.7 in Chapter 4. A decision tree was built in non-recursive manner.
The major steps involved in the implementation are similar to those in [Problem 4.3](https://github.com/Hatchin/Machine-Learning-Zhou_Zhihua/tree/master/Chap4/Problem4.3), including Entropy and Information Gain Calculation, Best Attribute Selection and Subdata splitted. 

However, the original recursive method is inefficient, especially when dealing with a large amount of data. To improve it, a non-recursive approach is adopted. In short, "stack" was used to build the tree and the feature, *Max Depth* was added to control the depth of a decision tree. 

The basic algorithm explaination and example code could be found:
- [Decision Tree with Non-Recursive Method](https://blog.csdn.net/yinchuandong2/article/details/41682293)

Based on the example code, the features of dealing with numeric value and max_depth are added to the new model.

