---
layout:     post
title:      What's big data
subtitle:   Public Speaking prepared speech (3min)
date:       2018-11-08
author:     Fernando
header-img: img/181108/header.jpg
catalog: false
tags:
    - Public speaking
---

In this era of big data, everyone is participating in some discussion about data mining, data cleaning, data processing balabala. So there got be necessity to talk about so-called “big data”.
By definition given by a data scientist Gartner, “big data is high-volume, high-velocity, and high variety information assets that demands effective, innovative processing methods for enhanced insight and decision making.”  Here is the problem, different from those traditional data sets, this time the size of data goes unimaginably large, what we can do and how we do it to make most use of it?

Here I am gonna talk about a particular method called “classification” and then follows an application in real life.

To do classification is to build a model or a function, which takes an unknown object as an input and then puts a meaningful tag on it. For example, here is a machine, for everyone passing by, it tells whether it is a man or a woman. That is to say, this kind of machine puts a tag of man/woman on a single object, which is a passer-by in this situation. Well concerning about the advantage of big data, the large amount. We can divide the data we own into two sets, the training dataset and the test dataset.  The training set is supposed be typical and of great variety. It is used to tell our model, which is very young and naive at the beginning, tell him what kind of characters this object will have, sort of telling him what kind of person is more likely to be a man, otherwise a woman.

This is just a simple case above, most of the time the tag may not be a binary value like man/woman ,red/black, true/false. Usually the tag we are talking about would be probabilities, you know, something like this person is 70% possible to be a man. Then comes a real-life application. Suppose a call center, let’s say China Mobile, now get a list of 100 people on hand. The salesman is ordered to find out at least 8 potential customers who are interested in China Mobile’s new product. The conventional way is that the poor salesman is gonna  go through the entire list and dial every number and have an unpleasant conversation with every impatient customer. However here we got a “big data” method, we use the historical sale data to train a model which will tell us everyone’s potential consuming motivation. After that we input that list of 100 bastards, the clever model will give us a list sorted by the descending order of their consuming potential. Now I do believe life would be much easier for that poor salesman.