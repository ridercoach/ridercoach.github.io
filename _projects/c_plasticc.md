---
layout: default
title: PLAsTiCC Astronomical Classification
abstract: Analyzing data from the Large Synoptic Survey Telescope.
---

## PLAsTiCC Astronomical Classification Challenge

The Large Synoptic Survey Telescope (LSST) being constructed in Chile is 
expected to discover 10 to 100 times more time-varying astronomical 
sources than ever before known. The goal of the Photometric LSST Astronomical 
Time-Series Classification Challenge was to develop algorithms to clasify these new objects.

One way to analyze time-series data is to feed the sequence of observations 
into a recurrent neural network.
 
This was tricky for this project, because 
the measurements in the different wavelengths were not synchronized, there 
were large gaps in the sampling, and for 
some classes of objects the time-varying behavior seemed not well represented. 

However, being curious, I created my first submission to the contest 
using a simple Keras 
LSTM network and some heavy-handed data cleaning. The accuracy 
of this approach, shown in 
the confusion matrix below, was 
less than stellar (haha.)

![](/images/cm.png)

An alternate approach is to reduce the 
sequence information to its time-varying attributes, 
such as frequencies, and use a non-recurrent neural network.

The figure below (inspired by Kaggler Siddhartha,) shows the potential 
value of such extracted characteristics.
On the left are the readings for one object in 
the training data, plotted as a function of time; the right-hand plot 
shows the same readings, but as a function of phase, based on frequencies 
extracted by the [Cesium](http://cesium-ml.org) method _featurize_time_series_.

![](/images/plasticc-615-plots.png)

Unfortunately, this processing is time-consuming, and by this point in my 
investigation there were not enough 
days left in the competition to perform it for all 3.5 million objects 
in the test set (at least not using the Kaggle environment.) Also, there was reason to 
expect that for some classes of objects this technique would not provide 
much leverage.

I thought about trying to be more clever in my 
preprocessing for the LSTM approach, or perhaps using Amazon 
Sagemaker, but the contest closed before I made any significant further progress.


