---
layout: post
title: '[Paper Review] 2021 - XNAP: Making LSTM-based Next Activity Predictions Explainable by Using LRP'
subtitle: XAI on Time Series Data
categories: xai
tags: ts
published: true
---
[Original Paper Link](https://arxiv.org/pdf/2008.07993.pdf){:target="_blank"}
[Github Link](https://github.com/fau-is/xnap){:target="_blank"}

**1. Introduction**

1) PBPM(Predictive Business Process Monitoring)
- 목적: 프로세스 운영 "성능을 높임"/"비용을 낮춤".
- 이벤트 로그를 기반으로 동작.
- ML 기반의 전통적인 방법들이 가진 성능 한계를 DL를 통해 개선할 수는 있으나 DL은 설명성(explainability) 부족 문제가 있음.
  --> DL이 제공하는 결과(출력)의 근거가 없으면 이를 수용/이용하기 어려울 수 있음.

<span style="color: green;">[Tim's Note] 시스템 로그 vs. 비지니스 이벤트 로그 and MES 로그</span>
비지니스 이벤트 로그 항목들 사이에는 강한 인과 관계가 존재하는 것으로 판단됨. 엄밀하게 말해 Syslog 같은 시스템 로그는 비지니스 이벤트 로그와는 다른 특성을 가진다고 생각됨. MES 트랜잭션 로그는 시스템 로그 보다는 비지니스 이벤트 로그에 가까울 것으로 생각됨.
  
2) 본 연구는 LRP(Layer-wise Relevance Propagation)을 이용해 LSTM의 비지니스 프로세스 상의 다음 행위 예측(next activity prediction)을 설명 가능하게 만드는 방법을 제안함. 

**2. Background**

1) Preliminaries

<figure>
  <img src="https://AllAboutXAI.github.io/assets/img/XAI/ts/2022-06-16-xai-ts-PaperReview_2_1.jpg" style="width:80%" class="center">
</figure>

2) LRP
- Post-hoc & Model-specific XAI Method
- LRP는 설명 대상 모델이 어떤 종류와 구성의 네트워크인가에 따라 구하는 실제 식(세부 내역)이 다르게 정의됨.
- [LRP에 대한 보다 자세한 소개](https://allaboutxai.github.io/xai/2022/06/15/xai-md_LRP/){:target="_blank"}

3) LRP for LSTM
- 본 논문은 <span style="font-weight:bold">Next Activity Prediction</span>을 위해 Many-to-one Weighted Linear Connection과 Two-to-one Multiplicative Interaction 두 가지 연결을 가지는 LSTM의 LRP를 계산하는 방법을 제안.
 
**3. Related Work on Explainable PBPM**

생략

**4. XNAP: Explainable Next Activity Prediction**

1) 학습
- 이벤트 로그에 대한 전처리, 레이블 생성 및 Onehot 인코딩, Bi-LSTM 사용
- 결과는 Softmax

2) 테스트(추론)

3) 실험 및 평가
- helpdesk event log와 bpi2019 데이터 사용
- 예측 성능
<figure>
  <img src="https://AllAboutXAI.github.io/assets/img/XAI/ts/2022-06-16-xai-ts-PaperReview_2_2.jpg" style="width:80%" class="center">
  <figcaption>Table. 2: Predictive quality of XNAP's Bi-LSTM model for the 10 folds.</figcaption>
</figure>
- 실행(분석)예
<figure>
  <img src="https://AllAboutXAI.github.io/assets/img/XAI/ts/2022-06-16-xai-ts-PaperReview_2_3.jpg" style="width:100%" class="center">
  <figcaption>Fig. 3: Activity relevances of XNAP's LRP.</figcaption>
</figure>

 <span style="color: green;">[Tim's Note]</span> 해당 이벤트 로그로 관련된 업무를 수행하는 담당자가 아니어서인지(도메인 경험/지식이 없어서인지) Fig. 3의 예와 같은 설명이 인상적이거나 도움이 크게 된다고 생각되지는 않음.