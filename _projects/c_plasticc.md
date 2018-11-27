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

One way to model sequential behavior is to feed the series of observations 
into a recurrent NN.
 
This is tricky for this project, because 
the measurements in the different passbands are not synchronized, there 
are large gaps in the sampling, and for 
some classes of objects the time-varying behavior seems not well represented. 

But being curious, I created my first submission to the contest 
using a simple Keras 
LSTM network and some heavy-handed tidying. The accuracy 
of this approach, shown in 
the confusion matrix below, is 
less than stellar (haha.)

![](/images/cm.png)

Alternatively, for time-series data, we can reduce the 
sequence information to its time-varying attributes, 
such as frequencies, and use a non-recurrent NN.

The figure below (inspired by Kaggler Siddhartha,) shows the potential 
value of such extracted characteristics.
On the left are the readings for one object in 
the training data, plotted as a function of time; the right-hand plot 
shows the same readings, but as a function of phase, based on frequencies 
extracted by the [Cesium](http://cesium-ml.org) method _featurize_time_series_.

![](/images/plasticc-615-plots.png)

Unfortunately, this analysis is time-consuming, and there are not enough 
days left in the competition to perform it for all 3.5 million objects 
in the test set (at least not using the Kaggle environment.) Also, not all 
classes of objects in the study are this well-behaved.

My ideas for the remaining time are: (a) try to be more clever in my 
preprocessing for the LSTM approach, and (b) perhaps try using Amazon 
Sagemaker, which would probably provide more compute power than is 
available in the Kaggle environment.


