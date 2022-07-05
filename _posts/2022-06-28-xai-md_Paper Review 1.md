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
- This work proposes <span style="color: green;">evaluating these attribution methods on semi-natural datasets:</span> natural datasets systematically modified to introduce ground truth information for attributions. <span style="font-weight:bold;">본 논문은 Feature Attribution Method를 평가할 수 있는 ground truth를 생성/정의하는 방법을 제안하고 제안한 방법의 유용성을 확인하기 위해 Saliency Map, Attention Mechanism, Rational Model에 적용해 봄.</span>

<span style="color: green;">[Tim's Note]</span> "Feature Arribution Method"의 번역
대체로 "특성 기여도 분석 방법"으로 번역하여 Attribution을 "기여도 분석"이라고 풀어 대입하고 있으나, "귀속"이라는 단어를 쓰는 것이 더 적절할 것으로 생각됨.

**2.1. Feature Attribution Methods**

1) <span style="font-weight:bold;">Saliency maps</span> explain a image I by producing S of same size, where S<sub>h, w</sub> indicates the contribution of pixel I<sub>h, w</sub>.

2) <span style="font-weight:bold;">Attention mechanisms</span> were orignally proposed to better retain sequential information. Recently they have been used as attribution values, but their validity is under debate with different and inconsistent criteria being proposed.

3) <span style="font-weight:bold;">Rational models</span> are inheretly interpretable models for text classificatin with a two-stage pipeline.

**2.2. Evaluation of Feature Attributions**

**3. Desiderata(Requirment/Prerequisite) for Attribution Values**

1) 모든 피처들을 고려한다면
- 각 피처의 귀속률(attribution percentage) Attr%는 다음과 같은 식으로 정의
<figure>
  <img src="https://AllAboutXAI.github.io/assets/img/XAI/md/2022-06-28-xai-md-PR_1.jpg" style="width:60%" class="center">
</figure>
D: 전체 피처 수, S<sub>i</sub>는 i번째 피처의 귀속 값
- 중요한 피처를 F<sub>C</sub>, 도움이 안되는(Non-informative) 피처를 F<sub>N</sub>라고 정의
- Attr%(F<sub>C</sub>)가 1에 가깝고, Attr%(F<sub>N</sub>)이 0에 가까워야 설명이 잘 되는 것으로 평가될 수 있음

2) Top k 피처
- 모든 피처에서 중요한 피처와 도움이 안되는 피처를 정확하게 구분해 내는 것은 쉽지 않은 일 --> Top k를 이용하는 방식 적용 가능 --> Top k를 이용하는 방식은 적절한 k를 선택하는 것이 이슈 --> k가 너무 작으면 중요한 피처가 누락될 수 있음, k가 너무 크면 중요하지 피처가 포함되어 방해를 할 수 있음
- 관련하여 정보 검색에서 사용되는 정확도, 재현율을 도입 적용할 수 있음 (본 논문이 선택한 방법임)
																													   
**4. Dataset Modification with Ground Truth**

**5. Evaluating Image Saliency Maps**

**6. Evaluating Text Attentions**

**7. Evaluating Text Rationals**

**8. Conclusion and Future Work**