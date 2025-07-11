---
title: Video Object Segmentation
permalink: /dataset/vos/
classes: wide
header:
  overlay_filter: rgba(232, 74, 39, 0.8)
  overlay_image: /assets/banner.jpg
sidebar:
  nav: "dataset"
---

## Overview
Semi-supervised video object segmentation targets at segmenting a particular object instance throughout the entire video sequence given only the object mask of the first frame. Different from previous video object segmentation datasets such as DAVIS, we will provide much larger scale of training and test data to foster various kinds of algorithms. In addition, our test dataset will have unseen categories which do not exist in the training dataset, in order to evaluate the generalization ability of algorithms.


## Dataset Statistics
Our dataset for video object segmentation was first released in 2018 in conjunction with a workshop challenge. In 2019, we further augment the dataset with more videos and object annotations (a subset of this dataset is carried out for the task of [video instance segmentation]({{ site.baseurl }}/dataset/vis/)).

**The 2018 version** was used for "[the 1st large-scale video object segmentation challenge]({{ site.baseurl }}/challenge/2018/)" at ECCV 2018. It contains three subsets. 
* Training: 3471 videos with dense (6 fps) object annotations, 65 categories and 5945 unique object instances.
* Validation: 474 videos,  65 training (seen) categories, 26 unseen categories and 894 unique object instances.
* Test: 508 videos, 65 training (seen) categories, 29 unseen categories and 915 unique object instances.

Please cite this version using the following bibtex:
```
@article{vos2018,
  author       = {Ning Xu and
                  Linjie Yang and
                  Yuchen Fan and
                  Dingcheng Yue and
                  Yuchen Liang and
                  Jianchao Yang and
                  Thomas S. Huang},
  title        = {YouTube-VOS: {A} Large-Scale Video Object Segmentation Benchmark},
  journal      = {CoRR},
  volume       = {abs/1809.03327},
  year         = {2018},
  url          = {http://arxiv.org/abs/1809.03327},
}
```
**The 2019 version** is used for "[the 2nd large-scale video object segmentation challenge]({{ site.baseurl }}/challenge/2019/)" at ICCV 2019. It augments the 2018 version with more videos and annotations.
* Training: 3471 videos, 65 categories and 6459 unique object instances.
* Validation: 507 videos, 65 training categories, 26 unseen categories and 1063 unique object instances. 
* Test: 541 videos, 65 training categories, 29 unseen categories and 1092 unique object instances.

Please cite this version using the following bibtex:

```
@misc{vos2019,
  author       = "Linjie Yang and Yuchen Fan and Ning Xu",
  title        = "The 2nd Large-scale Video Object Segmentation Challenge - video object segmentation track",
  month        = oct,
  year         = "2019",
}
```

**The 2022 version**  is used for “[the 4th large-scale video object segmentation challenge]({{site.baseurl }}/challenge/2022/)” at CVPR 2022. It augments the 2019 version with more videos and annotations in th testset.

* Training and Validation: same as the 2019 version.
* Test: 746 videos, 65 training categories, 29 unseen categories and 1409 unique object instances. Among them, we have 116 long videos with length at 20 - 120s, annotated at 1fps, with 116 object instances.

Please cite this version using the following bibtex:

```
@misc{vos2022,
  author       = "Linjie Yang and Yuchen Fan and Ning Xu",
  title        = "The 4th Large-scale Video Object Segmentation Challenge - video object segmentation track",
  month        = jun,
  year         = "2022",
}
```

## Evaluation
Following previous video object segmentation challenge [DAVIS](http://davischallenge.org/), we use Region Jaccard (J) and Boundary F measure (F) as our evaluation metrics. Differently, we evaluate the metrics on different sets of categories, i.e. seen and unseen, in order to evaluate the generalization ability of proposed methods. In detail,
* We compute J and F on both seen and unseen categories respectively, averaged over all corresponding objects.
* The final score is the average of the four scores: J for seen categories, F for seen categories, J for unseen categories, and F for unseen categories.

Note that in our videos, some objects first appear at middle frames instead of the first frame, be sure not to miss them! 

We have set up evaluation servers on CodaLab for the convenience of evaluating new algorithms. For more details of how to submit your results, please check the following links.
* ~~[Evaluation server for the 2019 version](https://competitions.codalab.org/competitions/20127)~~ [new](https://codalab.lisn.upsaclay.fr/competitions/6066).
* ~~[Evaluation server for the 2018 version](https://competitions.codalab.org/competitions/19544)~~ [new](https://codalab.lisn.upsaclay.fr/competitions/7685).


## Data Download
* ~~[2019 version](https://competitions.codalab.org/competitions/20127#participate-get_data)~~ [new](https://drive.google.com/drive/folders/1XwjQ-eysmOb7JdmJAwfVOBZX-aMbHccC?usp=sharing).
* ~~[2018 version](https://competitions.codalab.org/competitions/19544#participate-get-data)~~ [new](https://drive.google.com/drive/folders/1L9JAl1BCtzomRJ34tKsU9tJUmF-ZMFOM?usp=drive_link).
