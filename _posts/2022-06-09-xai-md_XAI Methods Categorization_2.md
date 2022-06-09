---
layout: post
title: 'XAI Methods Categorization'
subtitle: XAI Method
categories: xai
tags: md
published: true
---
**1. Transparency(투명성)**

1) DNN 등의 black-box 모델들이 투명성을 가질 수 있어야 함

2) 투명성: 모델이 동작하는 메커니즘을 바로 이해할 수 있어야 함

3) 의료, 자율 주행, 금융, 보안 등에서 모델의 투명성이 중요함

**2. Interpretability vs. Exaplainability**

1) Interpretability(해석가능성)
- 수동적인 관점에서 정의하는 것으로 모델이 사람에 의해 해석될 수 있는 정도를 말하는 것임(refers to a passive characteristic of a model referring to the level at which a given model makes sense for a human observer).

2) Explainability(설명가능성)
- 능동적인 관점에서 정의하는 것으로 모델이 내부 동작을 설명할 수 있는 정도를 말하는 것임(denoting any action or procedure taken by a model with the intent of clarifying or detailing its internal functions).

[Tim's Note] Reference #1이 Interpretability와 Explainability 및 관련/유사 용어(Understandability, Comprehensibility, Transparency)를 해당 논문 2장에서 설명하고 있는데, 명확하지가 않음(나의 언어 능력 부족에서 기인한 것일 수 있음 ^^). 저자들은 Transparency를 Interpretability와 연관짓고 있는데, Explainability와 연관되는 것으로 생각됨. 다시말해 스스로 설명을 제공할 수 있어야 Transparent Model이라고 분류될 수 있다고 생각함.

3) 청중(설명이 제공되어야 하는 또는 설명을 이해하려고 하는 대상)에 따라 설명가능성이나 해석가능성의 상세가 달라질 수 있다는 입장도 있음. 예를 들면 설명가능성은 청중이 "모델을 개발하는 엔지니어" 또는 "모델이 적용된 서비스를 사용하는 운영자(예를 들면 딥러닝 기반 통합 로그 분석 서비스의 고객)"이냐에 따라 그 상세 내용이 달라질 수 있음

4) 1)은 Post-hoc XAI, 2)는 Ante-hoc XAI로 연결되는 것이 맞다고 생각되나, Reference #1은 2.2의 결론에서 반대로 정의함

[Tim's Note] Interpretability와 Explainability는 여전히 혼돈을 주는 용어라고 판단이 되며, 내재 Intrinsic(Ante-hoc) 설명가능성과 사후(Post-hoc) 설명가능성이라는 용어가 가장 적절한 것으로 판단됨.

**References**

#1 [Explainable Artificial Intelligence (XAI): Concepts, taxonomies, opportunities and challenges toward responsible AI](https://arxiv.org/pdf/1910.10045.pdf){:target="_blank"}
  
##2 [Explainable AI: A Review of Machine Learning Interpretability Methods](https://www.mdpi.com/1099-4300/23/1/18){:target="_blank"}