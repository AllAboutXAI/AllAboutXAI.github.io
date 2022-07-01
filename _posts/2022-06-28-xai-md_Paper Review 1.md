---
layout: post
title: '[Paper Review] 2022 - Do Feature Attribution Methods Correctly Attribute Features?'
subtitle: XAI Method
categories: xai
tags: md
published: true
---
[Original Paper Link](https://arxiv.org/pdf/2104.14403.pdf){:target="_blank"}
[Github Link](https://github.com/YilunZhou/feature-attribution-evaluation){:target="_blank"}
[YouTube Link](https://www.youtube.com/watch?v=kAodFw6jvvo){:target="_blank"}

**1. Introduction**

1) Feature attribution methods
- like saliency maps are used to identify regions which are important for prediction.
- Does this truly work well? Not easy to answer, notably by a lack of ground truth.
- This work proposes <span style="color: green;">evaluating these attribution methods on semi-natural datasets:</span> natural datasets systematically modified to introduce ground truth information for attributions.

<span style="color: green;">[Tim's Note]</span> Feature Arribution Method 번역
대체로 "특성 기여도 분석 방법"으로 번역됨.

**2.1 Feature Attribution Methods**

1) <span style="font-weight:bold;">Saliency maps</span> explain a image I by producing S of same size, where S<sub>h, w</sub> indicates the contribution of pixel I<sub>h, w</sub>.
