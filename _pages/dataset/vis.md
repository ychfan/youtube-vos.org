---
title: Video Instance Segmentation
permalink: /dataset/vis/
classes: wide
header:
  overlay_filter: rgba(232, 74, 39, 0.8)
  overlay_image: /assets/banner.jpg
sidebar:
  nav: "dataset"
---

## Overview
Video instance segmentation  extends the image instance segmentation task from the image domain to the video domain. The new problem aims at **simultaneous detection, segmentation and tracking** of object instances in videos.  Given a test video,  the task requires not only the masks of all instances of a predefined category set to be labeled but also the instance identities across frames to be associated. A detailed explanation of the new task can be found in our [paper](https://arxiv.org/abs/1905.04804).

## Dataset Statistics
We collected the first large-scale dataset for video instance segmentation, called **YouTube-VIS**, which is based on our initial YouTube-VOS dataset. Specifically, our new dataset has the following features.
* 2,883 high-resolution YouTube videos
* A category label set including 40 common objects such as person, animals and vehicles
* 4,883 unique video instances
* 131k high-quality manual annotations

We split the YouTube-VIS dataset into 2,238 training videos, 302 validation videos and 343 test videos.

We believe YouTube-VIS can serve as a valuable benchmark for not only the video instance segmentation task, but also related tasks such as video semantic segmentation.


## Evaluation
We borrow the standard evaluation metrics in image instance segmentation with modification adapted to our new task. Specifically, the metrics are 
* **Average Precision (AP)**. AP is defined as the area under the precision-recall (PR) curve.  A confidence score (between 0 and 1) which measures the confidence of a predicted category for an instance  is needed to plot the PR curve. AP is averaged over multiple intersection-over-union (IoU) thresholds. We follow the COCO evaluation metrics to use 10 IoU thresholds from 50% to 95% at step 5%. 
* **Average Recall (AR)**. AR is defined as the maximum recall given some fixed number of segmented instances per video. 

Both of the two metrics are first evaluated per category and then averaged over the category set.

The only modification made to the two standard metrics for our new task is the IoU computation. Because differently from image instance segmentation, each instance in a video contains a sequence of masks. Therefore, the IoU computation is carried out not only in the spatial domain, but also in the temporal domain, i.e. the sum of intersection at every single frame over the sum of union at every single frame.

We have set up an evaluation server on CodaLab for the convenience of evaluating new algorithms. The submissions are ranked by Average Precision (AP). For more details of how to submit your results, please check the following link.
* [Evaluation server for the 2019 version.](https://competitions.codalab.org/competitions/23215)


## Data Download
* [2019 version.](https://competitions.codalab.org/competitions/23215#participate-get_data)
