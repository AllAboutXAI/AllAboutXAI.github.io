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

[Tim's Note] 시스템 로그 vs. 비지니스 이벤트 로그 and MES 로그
비지니스 이벤트 로그 항목들 사이에는 강한 인과 관계가 존재하는 것으로 판단됨. 엄밀하게 말해 Syslog 같은 시스템 로그는 비지니스 이벤트 로그와는 다른 특성을 가진다고 생각됨. MES 트랜잭션 로그는 시스템 로그 보다는 비지니스 이벤트 로그에 가까울 것으로 생각됨.
  
2) 본 연구는 LRP(Layer-wise Relevance Propagation)을 이용해 LSTM의 비지니스 프로세스 상의 다음 행위 예측(next activity prediction)을 설명 가능하게 만드는 방법을 제안함. 

**2. Background**

1) Preliminaries

<figure>
  <img src="https://AllAboutXAI.github.io/assets/img/XAI/ts/2022-06-07-xai-ts-PaperReview_2_1.jpg" style="width:80%" class="center">
</figure>

2) LRP for LSTM
