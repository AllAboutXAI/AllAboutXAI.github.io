---
layout: post
title: '[Paper Review] 2021 - XNAP: Making LSTM-based Next Activity Predictions Explainable by Using LRP'
subtitle: XAI on Time Series Data
categories: xai
tags: ts
published: true
---
[Original Paper Link](https://arxiv.org/pdf/2008.07993.pdf){:target="_blank"}

**1. Introduction**

1) PBPM(Predictive Business Process Monitoring)
- 목적: 프로세스 운영 "성능을 높임"/"비용을 낮춤".
- 이벤트 로그를 기반으로 동작.
- ML 기반의 전통적인 방법들이 가진 성능 한계를 DL를 통해 개선할 수는 있으나 DL은 설명성(explainability) 부족 문제가 있음.
  --> DL이 제공하는 결과(출력)의 근거가 없으면 이를 수용/이용하기 어려울 수 있음.

[Tim's Note] 시스템 로그 vs. 비지니스 이벤트 로그 and MES 로그
비지니스 이벤트 로그 항목들 사이에는 강한 인과 관계가 존재하는 것으로 판단됨. 엄밀하게 말해 Syslog 같은 시스템 로그는 비지니스 이벤트 로그와는 다른 특성을 가진다고 생각됨. MES 트랜잭션 로그는 시스템 로그 보다는 비지니스 이벤트 로그에 가까울 것으로 생각됨.
  
2) 본 연구는 LRP(Layer-wise Relevance Propagation)을 이용해 LSTM의 비지니스 프로세스 상의 다음 행위 예측(next activity prediction)을 설명 가능하게 만드는 방법을 제안함. 

**2. Background**

1) Preliminaries

<figure>
  <img src="https://AllAboutXAI.github.io/assets/img/XAI/ts/2022-06-07-xai-ts-PaperReview_2_1.jpg" style="width:70%" class="center">
</figure>

2) 안정성, 견고성, 확신성을 제공하는 XAI 방법론은 현재 없음

3) 안정성(Stability)
- 예를 들면 스티커가 붙어 있는 Stop 표지판을 잘 인식할 수 있어야 함
- 정확하게 인식은 못하더라도 최소 확신성 값이 낮게 표시되는 등 추가적인 관련 정보를 제공할 수 있어야 함

4) 확신성(Confidence)
- 소음이나 작은 변화를 충분히 잘 다룰 수 있도록 모델을 훈련시키는 것 또는 필요한 데이터 샘플을 제공하는 것은 사실상 불가능한 일이므로 테스트 데이터 샘플이 훈련에 사용된 데이터들의 분포와 얼마나 다른지를 정량적으로 평가하여 이를 확신성 점수로 제시하는 방법을 고려해 볼 수 있음

**3. XAI Techniques for Time Series**

1) Post-hoc Methods
- Post-hoc 방법은 입력(특성 값들)과 출력(예측 값) 사이의 관계를 추출해 모델의 동작에 가깝도록 함
  --> Post-hoc 방법들에는 모델 애그노스틱(Model-agnostic)과 모델 특화(Model-specific) 방법이 있음
- 이 논문에서 설명하는 시계열 데이터에 대한 Post-hoc XAI 방법은 모두 CNN 기반 
  --> 백프로퍼게이션(back-propagation) 기반 방법과 작은 변화(perturbation) 기반 방법이 있음
  
2) Ante-hoc Methods
- 모델 안에 설명과 관련된 정보가 함께 포함됨

3) Using "Backpropagation-based XAI for CNN" for Time Series Classification
- CAM (Class Activation Mapping) can highlight sub-sequences in the input time series that are maximally representative of a class.
  [Wang et al.](https://arxiv.org/pdf/1611.06455.pdf?ref=https://githubhelp.com){:target="_blank"} 
  [Fawaz et al.](https://arxiv.org/pdf/1908.07319.pdf){:target="_blank"}
  [Oviedo et al.](https://www.nature.com/articles/s41524-019-0196-x.pdf?origin=ppub){:target="_blank"}
- Gradient*Input
  [Siddiqui et al.](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8695734){:target="_blank"} 
  [Strodthoff et al.](https://arxiv.org/pdf/1806.07385.pdf){:target="_blank"}
  [Cho et al.](https://arxiv.org/pdf/2004.12538.pdf){:target="_blank"}
  
4) Using "Perturbation-based XAI for CNN" for Time Series Classification
- Perturbation-based methods directly compute the contribution of the input features by removing, masking, or altering them, running a forward pass on the new input, and measuring the difference with the original input.
- can be used for both classification and regression tasks.

5) Usng "Attention Mechanism" for Time Series Classification
- Attention mechanisms can be used for time series classification [Karim al.](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8141873){:target="_blank"} or time series forecasting [Schockaert et al.](https://arxiv.org/ftp/arxiv/papers/2007/2007.12617.pdf){:target="_blank"}
- Attention mechanisms are Ante-Hoc explainability methods.

6) Usng "SAX(Symbolic Aggregate Approximation), a Data Mining Approach," for Time Series Classification
- SAX transforms the input time series into strings.
- [Senin and Malinchik](https://apps.dtic.mil/sti/pdfs/ADA603196.pdf){:target="_blank"} and [Le Nguyen et al](https://arxiv.org/pdf/1808.04022.pdf){:target="_blank"} extend SAX to perform time series classification

7) Usng "Fuzzy Logic, a Data Mining Approach," for Time Series Forecasting/Prediction

8) Explaining Models through Representative Examples for Time Series Classification

**4. Explanations Scale**

1) The explanations are qualified as local when they are valid for a specific sample, and as global when they are valid for a set of samples or for the entire dataset.

2) Local Explanations
- XAI methods for CNN naturally produce local explanations.
- For RNN, the explanations are local if the internal states represent one instance, or global if the internal states represent several instances.

3) Global Explanations
- Some papers extend the methods generating local explanations to produce global explanations.
- Some methods provide global explanations through the usage of clustering.

**5. Evaluating Explanations**

1) This is about how to assess the quality of explanations.

2) Qualitative Evaluations
- It could be by domain experts.
- But, the unintuitive nature of time series make it difficult even for domain experts to qualitatively assess the quality of the explanations generated.

3) Quantiative Evaluations
- [Tonekaboni et al.](https://openreview.net/pdf?id=HygDF1rYDB){:target="_blank"}, [Cho et al.](https://arxiv.org/pdf/2004.12538.pdf){:target="_blank"}
- [Arnout et al.](https://arxiv.org/pdf/1909.07082.pdf){:target="_blank"} propose two new quantitative evaluation methods to overcome the limitations of the perturbation approach, which has a lack of evaluation of trends or patterns in the time series.

**6. Discussion**

1) Most methods presented in this survey indicate which specific regions of the input data get attention from the model while classification is performed. They do not provide any confidence in the model, neither mitigates its vulnerabilities.

2) However, the trust brought by these methods can be questioned by the unintuitive aspect of time series.
