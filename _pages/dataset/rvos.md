---
title: Referring Video Object Segmentation
permalink: /dataset/rvos/
classes: wide
header:
  overlay_filter: rgba(232, 74, 39, 0.8)
  overlay_image: /assets/banner.jpg
sidebar:
  nav: "dataset"
---

## Overview
Referring video object segmentation aims at segmenting an object in video with language expressions. Unlike the previous video object segmentation, the task exploits a different type of supervision, language expressions, to identify and segment an object referred by the given language expressions in a video. A detailed explanation of the new task can be found in the following paper.
* Seonguk Seo, Joon-Young Lee, Bohyung Han, “URVOS: Unified Referring Video Object Segmentation Network with a Large-Scale Benchmark”, European Conference on Computer Vision (ECCV), 2020 [[PDF]](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123600205.pdf)

**Important Announcement**: Unlike prior Youtube-VOS challenges, the Refer-Youtube-VOS challenge winners will be **required** to release the experimental codes to replicate their results. The detailed procedure for releasing the code is to be determined.

## Dataset Statistics
We collected the large-scale dataset for referring video object segmentation, called **Refer-YouTube-VOS**, which is based on YouTube-VOS-2019 dataset. Specifically, our new dataset has
* 3,978 high-resolution YouTube videos
* 131k high-quality manual annotations
* 15k language expressions

We split the YouTube-VOS dataset into 3,471 training videos, 202 validation videos and 305 test videos. Note that the splits have changed from Youtube-VOS-2019.



## Evaluation
Following the previous video object segmentation challenge Youtube-VOS, we use Region Jaccard (J) and Boundary F measure (F) as our evaluation metrics. We compute J and F, averaged over all corresponding expressions.

We have set up evaluation servers on CodaLab for the convenience of evaluating new algorithms. For more details of how to submit your results, please check the following links.
* [Evaluation server for the 2021 version.](https://competitions.codalab.org/competitions/29129)


## Data Download
* [2021 version.](https://competitions.codalab.org/competitions/29129#participate-get_data)
