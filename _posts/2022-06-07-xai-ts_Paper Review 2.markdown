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
  <img src="https://AllAboutXAI.github.io/assets/img/XAI/ts/2022-06-07-xai-ts-PaperReview_2_1.jpg" style="width:80%" class="center">
</figure>

2) LRP for LSTM


