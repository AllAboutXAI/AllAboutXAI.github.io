---
layout: post
title: 'XAI Methods Categorization'
subtitle: XAI Method
categories: xai
tags: md
published: true
---
**References**

#1 [Explainable Artificial Intelligence (XAI): Concepts, taxonomies, opportunities and challenges toward responsible AI](https://arxiv.org/pdf/1910.10045.pdf){:target="_blank"}
  
#2 [Explainable AI: A Review of Machine Learning Interpretability Methods](https://www.mdpi.com/1099-4300/23/1/18){:target="_blank"}

**1. Introduction**

1) Transparency(투명성)
- DNN 등의 black-box 모델들이 투명성을 가질 수 있어야 함
- 투명성: 모델이 동작하는 메커니즘을 바로 이해할 수 있어야 함
- 의료, 자율 주행, 금융, 보안 등에서 모델의 투명성이 중요함

**2. Taxonomy**

1) Interpretability(해석가능성)
- 수동적인 관점에서 정의하는 것으로 모델이 사람에 의해 해석되는 정도를 말하는 것임 (refers to a passive characteristic of a model referring to the level at which a given model makes sense for a human observer).

2) Explainability(설명가능성)
- 능동적인 관점에서 정의하는 것으로 모델이 내부 동작을 설명하는 정도를 말하는 것임 (denoting any action or procedure taken by a model with the intent of clarifying or detailing its internal functions).

[Tim's Note] Reference #1이 Interpretability와 Explainability 및 유사 용어를 해당 논문 2장에서 설명하고 있는데, 명확하지가 않음(언어 능력 부족에서 기인한 것일 수 있음 ^^). 저자들은 Transparency를 Interpretability와 연관짓고 있는데, Explainability와 연관되는 것으로 생각됨. 다시말해 스스로 설명을 제공할 수 있어야 Transparent Model이라고 분류될 수 있다고 판단됨.