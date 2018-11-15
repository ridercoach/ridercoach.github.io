---
layout: default
title: PLAsTiCC Astronomical Classification
abstract: Analyzing data from the Large Synoptic Survey Telescope.
---

## PLAsTiCC Astronomical Classification Challenge

The goal of the Photometric LSST Astronomical Time-Series Classification 
Challenge is to develop algorithms to process the huge stream of data 
that will come from a unique new telescope being constructed in Chile, 
expected to discover 10 to 100 times more time-varying astronomical 
sources than ever before known.  The time-series nature of this data 
will be a good application for some kind of recurrent neural network.
 
From various discussions and kernels on Kaggle it appears that 
some competitors are using approaches that don't necessarily rely on the 
time-series nature of the observations, and they are getting good 
results.  However, I want to use this competition as an opportunity to 
improve my skills in sequential data.  At this point I am thinking 
about using a Keras model with an LSTM layer, and I am currently 
working on transforming the data into a suitable structure for this.

My first public [kernel](https://www.kaggle.com/ridercoach/crude-binary-attempt-w-raw-time-series-data) 
for this project uses a greatly-simplified approach in order to get 
a working model which I can then build on. Despite the crudity of it, 
I got 73% accuracy using only a very small portion of the time-series 
data.

The next steps will be to extend this binary classifier to handle all 
the target classes so that I can make my first submission to the 
contest, and then work on feature engineering to improve the accuracy.



