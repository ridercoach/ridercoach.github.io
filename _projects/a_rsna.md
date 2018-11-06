---
layout: default
title: Kaggle RSNA Pneumonia Detection Challenge
abstract: Training YOLOv2 to scan chest x-rays.
---

## Kaggle RSNA Pneumonia Detection Challenge

I used the Darknet framework with the "regular" version of the YOLOv2 model.
I started with the yolov2.weights file and trained for 12,300 iterations
with 2000 (1400 training, 600 test) of the labeled images provided by RSNA.
I did the training on an AWS p2.xlarge EC2 instance, which took
about 24 hours. I scored .098 (top score .260). 

In the sample x-ray below, the radiologist diagnosis is shown in blue, 
and the prediction of the model in pink.  This particular image, though 
from the labeled training set, was not used for training the model, so 
it is a fair assessment.

Further details about my procedure are available
[here](https://github.com/ridercoach/rsna2018).

![](/images/rsna-sample.png)

 
