---
layout: post
title: '[Paper Review] Explainable Artificial Intelligence (XAI) on Time Series Data - A Survey'
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

1) XAI 방법론의 목적들
- 설명성(Explainability): 모델 내부 동작 및 그 동작의 이유를 모델이 제공함
- 해석성(Interpretability): 모델의 동작을 사람이 이해할 수 있음
- 신뢰성(Trusworthiness): 모델이 의도/기대한 대로 동작할 것임을 확신할 수 있음
- 상호작용성(Interactivity): 사람과 상호작용함
- 안정성(Stability): 입력이나 모델에 작은 변화가 가해져도 모델이 크게 영향을 받지 않음
- 견고성(Robustness): 의도적인 공격에 모델이 크게 영향을 받지 않음
- 재현성(Reproducibility): 동일한 데이터셋에 대해 여러번 실행되었을 때 유사한 결과가 나옴
- 확신성(Confidence): 모델이 내놓은 결과를 확신할 수 있는 지 여부를 정량적(확률적)으로 평가함

<figure>
  <img src="https://AllAboutXAI.github.io/assets/img/XAI/ts/2022-06-02-xai-ts-PaperReview_1_1.jpg" alt="Fig 2" style="width:30%">
  <figcaption>Fig. 2: XAI 방법론의 목적들의 상호 관계</figcaption>
</figure>

[Tim's Note] XAI 관련 용어는 표준적인 정의가 있다고 보기 어려움

2) 안정성, 견고성, 확신성을 제공하는 XAI 방법론은 현재 없음

3) 안정성(Stability)
- 예를 들면 스티커가 붙어 있는 Stop 표지판을 잘 인식할 수 있어야 함
- 정확하게 인식은 못하더라도 최소 확신성 값이 낮게 표시되는 등 추가적인 관련 정보를 제공할 수 있어야 함
