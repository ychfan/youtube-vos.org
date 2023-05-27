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

**The 2019 version** was used for "[the 2nd large-scale video object segmentation challenge]({{ site.baseurl }}/challenge/2019/)" at ICCV 2019.
* 2,883 high-resolution YouTube videos, 2,238 training videos, 302 validation videos and 343 test videos
* A category label set including 40 common objects such as person, animals and vehicles
* 4,883 unique video instances
* 131k high-quality manual annotations

Please cite this version using the following bibtex:
```
@inproceedings{ Yang2019vis,
    author = {Linjie Yang and Yuchen Fan and Ning Xu},
    title = {Video instance segmentation},
    booktitle = {ICCV},
    year = {2019},
 }
```
**The 2021 version** was used for "[the 3rd large-scale video object segmentation challenge]({{ site.baseurl }}/challenge/2021/)" at CVPR 2021.
* 3,859 high-resolution YouTube videos, 2,985 training videos, 421 validation videos and 453 test videos.
* An improved 40-category label set by merging eagle and owl into bird, ape into monkey, deleting hands, and adding flying disc, squirrel and whale
* 8,171 unique video instances
* 232k high-quality manual annotations

Please cite this version using the following bibtex:
```
@misc{vis2021,
  author       = "Linjie Yang and Yuchen Fan and Yang Fu and Ning Xu",
  title        = "The 3rd Large-scale Video Object Segmentation Challenge - video instance segmentation track",
  month        = jun,
  year         = "2021",
}
```
**The 2022 version** was used for "[the 4th large-scale video object segmentation challenge]({{ site.baseurl }}/challenge/2022/)" at CVPR 2022 and "[the 5th large-scale video object segmentation challenge]({{ site.baseurl }}/challenge/2023/)" at ICCV 2023.
* 71 additional long videos in validation and 89 additional long videos in test set, with additional separate evaluation
* 259 additional unique video instances in validation and 268 additional video instances in test
* 33597 high-quality masks
* The additional long videos (L) are separately evaluated from previous videos (S), and the final mAP is the average of mAP_L and mAP_S

Please cite this version using the following bibtex:

```
@misc{vis2022,
  author       = "Linjie Yang and Yuchen Fan and Ning Xu",
  title        = "The 4th Large-scale Video Object Segmentation Challenge - video instance segmentation track",
  month        = jun,
  year         = "2022",
}
```
We believe YouTube-VIS can serve as a valuable benchmark for not only the video instance segmentation task, but also related tasks such as video semantic segmentation.


## Evaluation
We borrow the standard evaluation metrics in image instance segmentation with modification adapted to our new task. Specifically, the metrics are 
* **Average Precision (AP)**. AP is defined as the area under the precision-recall (PR) curve.  A confidence score (between 0 and 1) which measures the confidence of a predicted category for an instance  is needed to plot the PR curve. AP is averaged over multiple intersection-over-union (IoU) thresholds. We follow the COCO evaluation metrics to use 10 IoU thresholds from 50% to 95% at step 5%. 
* **Average Recall (AR)**. AR is defined as the maximum recall given some fixed number of segmented instances per video. 

Both of the two metrics are first evaluated per category and then averaged over the category set.

The only modification made to the two standard metrics for our new task is the IoU computation. Because differently from image instance segmentation, each instance in a video contains a sequence of masks. Therefore, the IoU computation is carried out not only in the spatial domain, but also in the temporal domain, i.e. the sum of intersection at every single frame over the sum of union at every single frame.

We have set up an evaluation server on CodaLab for the convenience of evaluating new algorithms. The submissions are ranked by Average Precision (AP). For more details of how to submit your results, please check the following link.
* [Evaluation server for the 2022 version](https://codalab.lisn.upsaclay.fr/competitions/3410).
* ~~[Evaluation server for the 2021 version](https://competitions.codalab.org/competitions/28988)~~ [new](https://codalab.lisn.upsaclay.fr/competitions/7680).
* ~~[Evaluation server for the 2019 version](https://competitions.codalab.org/competitions/20128)~~ [new](https://codalab.lisn.upsaclay.fr/competitions/6064).


## Data Download
* [2022 version](https://codalab.lisn.upsaclay.fr/competitions/3410#participate-get_data).
* ~~[2021 version](https://competitions.codalab.org/competitions/28988#participate-get_data)~~ [new](https://codalab.lisn.upsaclay.fr/competitions/7680#participate-get_data).
* ~~[2019 version](https://competitions.codalab.org/competitions/20128#participate-get_data)~~ [new](https://codalab.lisn.upsaclay.fr/competitions/6064#participate-get_data).
