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
대체로 "특성 기여도 분석 방법"으로 번역하여 Attribution을 "기여도 분석"이라고 풀어 대입하고 있으나, "귀속"이라는 단어를 쓰는 것이 더 적절할 것으로 생각됨.

**2.1. Feature Attribution Methods**

1) <span style="font-weight:bold;">Saliency maps</span> explain a image I by producing S of same size, where S<sub>h, w</sub> indicates the contribution of pixel I<sub>h, w</sub>.

2) <span style="font-weight:bold;">Attention mechanisms</span> were orignally proposed to better retain sequential information. Recently they have been used as attribution values, but their validity is under debate with different and inconsistent criteria being proposed.

3) <span style="font-weight:bold;">Rational models</span> are inheretly interpretable models for text classificatin with a two-stage pipeline.

**2.2. Evaluation of Feature Attributions**

**3. Desiderata(Requirment/Prerequisite) for Attribution Values**

1) 모든 피처들을 고려한다면
- 중요한 피처를 F<sub>C</sub>, 도움이 안되는(Non-informative) 피처를 F<sub>N</sub>라고 정의
- 각 피처의 귀속률(attribution percentage) Attr%는 다음과 같은 식으로 정의
<figure>
  <img src="https://AllAboutXAI.github.io/assets/img/XAI/md/2022-06-28-xai-md-PR_1.jpg" style="width:80%" class="center">
</figure>
D: 전체 피처 수, S<sub>i</sub>는 i번째 피처의 귀속 값
- Attr%(F<sub>C</sub>)가 1에 가깝도록, Attr%(F<sub>N</sub>)이 0에 가까워야 설명이 잘 되는 것으로 평가될 수 있음 
																													   
**4. Dataset Modification with Ground Truth**

