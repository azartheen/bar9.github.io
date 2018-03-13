---
layout: post
title: "Part 1 of ML Series: Accessible Machine Learning"
author: Roland Brand
published: false
---

Not long ago Machine Learning used to be pretty "academic" in the sense that the only way to access
it was through formal mathematical notation. Machine Learning is the heartpiece of the still new
profession of __data scientist__, dubbed the _sexiest job of the 21st century_. So far, this sexiness has
become pretty accessible.

This article assumes that you have a rough idea what data science and machine learning are, and that you have
heard about R and Python with Scikit-Learn being popular languages for data science. If you haven't, read it up
...here...

## Jupyter Notebooks
The medium __Jupyter Notebook__ is a breakthrough in documentation of data science. It is 
__interactive documentation__.
* Linear
* At any step you can inspect intermediary steps (since it is an interpreter context)
* Graphical output, which is paramount for inspecting data, is rendered directly into the notebook
* Notebooks can be viewed on Github without rebuilding the runtime locally.

## Kaggle Datasets and Challenges
* Repeatable, same format
* Competitive environement / Marketplace for data analysis
* Catalysator for best practices
* Convergence, general data science workflows
  * data gathering
  * data cleansing
  * train
  * test
  * predict
* uniform interfaces for algorithms / libraries

## Consequences
* Many kernels publicly available
  * n Kaggle kernels,
  * n github notebooks
* ML models behave more and more like software libraries
  * Devs need to be aware how their interfaces work
* Devs need to integrate ML models to apps; dissemination
  -> next article will be about serving a simple ML model as a rest api.


## Consequences
