# Chapter 8 Problem 8.3 
## Implementation of AdaBoost classifier

This repository contains my personal notes and codes for problem 8.3 in Chapter 8. A Ensemble Classifier using AdaBoost algorithm for a two-class classification problem is implemented.

The algorithm sequentially applies a weak classification to modified versions of the data. By increasing the weights of the missclassified observations, each weak learner focuses on the error of the previous one. The predictions are aggregated through a weighted majority vote. 

The main steps are as follows:
<br />
<img src="https://github.com/Hatchin/Machine-Learning-Zhou_Zhihua/blob/master/EnsembleLearning/AdaBoost/adaboost_algo.png" width="600"> <br />



