---
title: "Machine Learning"
date: 2018-09-26
tags: []
categories: []
---


## Linear Regression?

For an $n$ dimensional vector $\mathbf{x}$, the result is $y$. 
Find the coefficient $\boldsymbol{\Theta}$ which minimize $\frac{1}{2}\sum_j^m (y-\boldsymbol{\Theta\mathbf{x})^2$.

using gradient descent method to get the result iteratively
$$\Theta ：= \Theta -\alpha \sum (y-\boldsymbol{\Theta\mathbf{x})\mathbf{x}$$


* batch gradient descent : use the whole data set to train the model
* stochastic gradient descent : use one or part of the data set to train each step; fast but not guarantee the convergency

closed form of the result : $$\Theta = (\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T Y$$






