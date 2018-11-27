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
sources than ever before known. 
 
Using the sequence data for this project is tricky, because 
the measurements in the different passbands are not synchronized, there 
are large gaps in the data, and for 
some classes of objects the time-varying behavior simply seems unclear from 
the data.

But being curious, I made my first submission using a simple Keras 
LSTM network and some heavy-handed cleaning of the data. The accuracy 
of this approach, shown in 
the confusion matrix below, was 
less than stellar (haha.)

![](/images/cm.png)

Another way to handle sequence information, especially in a situation 
like this, is to "featurize" it by using a package such as Cesium to 
extract parameters such as frequencies. In the figure below (inspired 
by Kaggler Siddhartha,) the left-hand plot shows the readings for one object in 
the training data, plotted as a function of time; the right-hand plot 
shows the same readings, but as a function of phase, based on a frequency 
extracted by a Cesium method.

![](/images/plasticc-615-plots.png)

Unfortunately, this analysis is time-consuming, and there are not enough 
days left in the competition to perform it for all 3.5 million objects 
in the test data.

My ideas for the remaining time are: (a) try to be more clever in my 
preprocessing for the LSTM approach, and (b) perhaps try using Amazon 
Sagemaker, which would probably provide more compute power than is 
available in the Kaggle environment.


