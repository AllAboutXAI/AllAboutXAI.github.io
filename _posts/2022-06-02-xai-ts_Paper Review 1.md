---
layout: post
title: '[Paper Review] 2021- Explainable Artificial Intelligence (XAI) on Time Series Data - A Survey'
subtitle: XAI on Time Series Data
categories: xai
tags: ts
published: true
---
[Original Paper Link](https://arxiv.org/pdf/2104.00950.pdf){:target="_blank"}

**1. Introduction**

1) Main tasks by the ML methods applied to time series: classification, forecasting, clustering

2) DL architecture to deal with time series data
- RNN 계열, CNN 계열, Transformers
- Lack of interpretability

3) 시계열 데이터에 대한 XAI가 쉽지 않은 이유
- 시계열 데이터는 직관적이지 않음 (사람에게도 시계열 데이터를 직관적으로 해석하는 것은 어려운 일일 때가 많음)
- 현재까지 진행된 연구들은 입력의 어떤 부분(part)이 출력에 영향을 주는 지를 찾아내고 나타내는 것에 집중되어 있음

**2. XAI Terminology and Definitions**

[Tim's Note] XAI 관련 용어는 표준적인 정의가 있다고 보기 어려움

1) XAI 방법론의 목적들
- 설명성(Explainability): 모델 내부 동작 및 그 동작의 이유를 모델이 제공함
- 해석성(Interpretability): 모델의 동작을 사람이 이해할 수 있음
- 신뢰성(Trusworthiness): 모델이 의도/기대한 대로 동작할 것임을 확신할 수 있음
- 상호작용성(Interactivity): 사람과 상호작용함
- 안정성(Stability): 입력이나 모델에 작은 변화(perturbation)가 가해져도 모델이 크게 영향을 받지 않음
- 견고성(Robustness): 의도적인 공격에 모델이 크게 영향을 받지 않음
- 재현성(Reproducibility): 동일한 데이터셋에 대해 여러번 실행되었을 때 유사한 결과가 나옴
- 확신성(Confidence): 모델이 내놓은 결과를 확신할 수 있는 지 여부를 정량적(확률적)으로 평가함

<figure>
  <img src="https://AllAboutXAI.github.io/assets/img/XAI/ts/2022-06-02-xai-ts-PaperReview_1_1.jpg" alt="Fig 2" style="width:70%" class="center">
  <figcaption>Fig. 2: XAI 방법론의 목적들의 상호 관계</figcaption>
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
- Attention mechanisms are Ante-hoc explainability methods.

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

3) Quantitative Evaluations
- [Tonekaboni et al.](https://openreview.net/pdf?id=HygDF1rYDB){:target="_blank"}, [Cho et al.](https://arxiv.org/pdf/2004.12538.pdf){:target="_blank"}
- [Arnout et al.](https://arxiv.org/pdf/1909.07082.pdf){:target="_blank"} propose two new quantitative evaluation methods to overcome the limitations of the perturbation approach, which has a lack of evaluation of trends or patterns in the time series.

**6. Discussion**

1) Most methods presented in this survey indicate which specific regions of the input data get attention from the model while classification is performed. They do not provide any confidence in the model, neither mitigates its vulnerabilities.

2) However, the trust brought by these methods can be questioned by the unintuitive aspect of time series.
