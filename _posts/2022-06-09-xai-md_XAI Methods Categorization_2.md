---
layout: post
title: 'XAI Methods Categorization'
subtitle: XAI Method
categories: xai
tags: md
published: true
---
**1. Taxonomy**

1) XAI 관련 표준이라 할 수 있는 taxonomy는 존재하지 않음.

2) 개인적으로 Reference 3의  Mind-map이 전체적인 그림을 잘 보여주는 버전이라고 생각함.

<figure>
  <img src="https://AllAboutXAI.github.io/assets/img/XAI/md/2022-06-09-xai-md-XAI Method Categorization_2_1.jpg" alt="Fig 2" style="width:85%" class="center">
  <figcaption>Fig. 2: Taxonomy mind-map of Machine Learning Interpretability Techniques</figcaption>
</figure>

**2. Transparent Model**

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

**3. Post-hoc Explainability**

1) 여러 방법들이 가능함: Text Explanation, Visual Explanation, Local Explanation, Explanation by Example, Explanation by Simplification, Feature Relevance Explanation --> 사람들이 어떤 것을 설명하는 방식들임.

2) Model-agnostic and Model-specific Methods

3) <span style="color: blue;">Model-agnositic Post-hoc Method 1:</span> <span style="color: red;">Explanation by Simplification</span>
- Almost all techniques taking this path for model simplification are based on rule extraction techniques.
- <span style="font-weight:bold">LIME</span>(Local Interpretable Model-agnostic Explanations) builds locally linear models around the predictions of an opaque model to explain it.
- G-REX, etc

4) <span style="color: blue;">Model-agnositic Post-hoc Method 2:</span> <span style="color: red;">Feature Relevance Explanation</span>
- aims to describe the functioning of an opaque model by ranking or measuring the influence, relevance or importance each feature has in the prediction output by the model to be explained.
- <span style="font-weight:bold">SHAP</span>(SHapley Additive exPlanations)
- Etc

5) <span style="color: blue;">Model-agnositic Post-hoc Method 3:</span> <span style="color: red;">Visual Explanation</span>

6) <span style="color: green;">Post-hoc Method for Shallow ML Model 1:</span> <span style="color: red;">Tree Ensembles, Random Forests</span>
- Tree Ensemble: To circumvent the issue of single tree's overfitting 
- Methods Using "Explanation by Simplification" and/or "Feature Relevance Exaplanation"

7) <span style="color: green;">Post-hoc Method for Shallow ML Model 2:</span> <span style="color: red;">Support Vector Machine</span>
- Post-hoc explainability applied to SVMs covers explanation by simplification, local explanations, visualizations and explanations by example.

8) <span style="color: magenta">Post-hoc Method for DL 1:</span> <span style="color: red;">Multi-layer NN(MLP)</span>
- Model Simplification Method: DeepRED, etc
- Feature Revelavnce Method: DeepLIFT, etc

9) <span style="color: magenta">Post-hoc Method for DL 2:</span> <span style="color: red;">CNN</span>
- Two major approaches: 1) Those that try to understand the decision process by mapping back the output in the input space to see which parts of the input were discriminative for the output, 2) Those that try to delve inside the network and interpret how the intermediate layers see the external world, not necessarily related to any specific input, but in general.
- Approach 1: CAM(Class Activation Map), Heatmap Usinig LRP, Grad-CAM(Gradient-weighted CAM), Attribution
- Approach 2: A Method Reconstructing the Visual Information Contained Inside the CNN
- Others: Text Explanation(e.g. combining a CNN feature exatractor with an RNN attention model), Using LIME
- Visualization mixed with feature relevance methods are the most adopted approach to explainability in CNNs

10) <span style="color: magenta">Post-hoc Method for DL 3:</span> <span style="color: red;">RNN</span>
- Two major approaches: 1) explainability by understanding what a RNN model has learned (mainly via feature relevance methods, 2) explainability by modifying RNN architectures to provide insights about the decisions they make (local explanations)
- Approach 1: Using LRP, Etc
- Approach 2: RETAIN, Etc

**References**

1. [Explainable Artificial Intelligence (XAI): Concepts, taxonomies, opportunities and challenges toward responsible AI](https://arxiv.org/pdf/1910.10045.pdf){:target="_blank"}
  
2. [Explainable AI: A Review of Machine Learning Interpretability Methods](https://www.mdpi.com/1099-4300/23/1/18){:target="_blank"}