---
layout: post
title: 'XAI Methods Categorization'
subtitle: XAI Method
categories: xai
tags: md
published: true
---
**1. Transparent Model**

1) 모델 자체로 (Intrinsic/Ante-hoc) Explainability 제공.

2) Three Levels of Transparency
- Algorithmic Transparency, Decomposability, and Simulatability --> 각각의 상세 설명은 Reference 1의 2.5.1.에서 확인.
- Simulatability나 Decomposability가 어떤 의미가 있는지 모르겠음. 
- Transparent Model이라고 하면 보통 Algorithmic Transparency를 이야기하는 것으로 생각됨. Algorithmic Transparency를 가지는 예 --> 선형 모델

3) Linear/Logistic Regression
- "Logistic Regression is a classification model to predict a dependent variable(category) that is dichotomous(binary). Howerver, when the dependent variable is continuous, linear regression would be its homonym."
- Explanation Using Statistics, Visualization

4) Decision Trees
- Resgression, Classification
 
5) K-Nearest Neighbors(KNN)
- Classification, Regression

6) Rlue-based Learning

7) General Additive Models

8) Bayesian Models

**2. Post-hoc Explainability**

1) 여러 방법들이 가능함: Text Explanation, Visual Explanation, Local Explanation, Explanation by Example, Explanation by Simplification, Feature Relevance Explanation --> 사람들이 어떤 것을 설명하는 방식들임.

2) Model-agnostic and Model-specific Methods

3) Model-agnositic Post-hoc Method 1: <span style="color: red;">Explanation by Simplication</span>

**References**

1. [Explainable Artificial Intelligence (XAI): Concepts, taxonomies, opportunities and challenges toward responsible AI](https://arxiv.org/pdf/1910.10045.pdf){:target="_blank"}
  
2. [Explainable AI: A Review of Machine Learning Interpretability Methods](https://www.mdpi.com/1099-4300/23/1/18){:target="_blank"}