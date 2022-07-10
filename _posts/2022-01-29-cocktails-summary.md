---
layout: distill
title: "Paper summary: Regularization Cocktails"
description: A short summary of 'Well-tuned Simple Nets Excel on Tabular Datasets' by Arlind Kadra et al. 
date: 2022-01-29
show: true

authors:
  - name: Akkapaka Saikiran
    url: "https://akkapakasaikiran.github.io/" 
    affiliations:
      name: CSE, IIT Bombay

---


Resources: 
[ArXiv](https://arxiv.org/abs/2106.11189) | 
[OpenReview](https://openreview.net/forum?id=d3k38LTDCyO) | 
[GitHub](https://github.com/releaunifreiburg/WellTunedSimpleNets)

**One-liner:** 
Picking regularizers and hyperparameters in a principled manner leads to neural networks that perform well on tabular data.

**Context:** 
Deep learning (DL) has led to advances in tasks involving raw data (vision, speech, text). However, for tabular data ─ which is ubiquitous in practice ─ gradient-boosted decision trees (GBDTs) generally outperform neural networks.   

**Summary:** 
The authors claim that combining regularization techniques for MLPs in a principled, dataset-specific manner can result in state-of-the-art (SoTA) performance. Hyperparameter optimization (HPO) is common in practice and also an active area of research, but regularizers are still allegedly picked in an ad-hoc manner. So the authors pose the problem of finding the best combination of regularizers as a search over the combined hyperparameter space of 13 common regularizers. This combination is called a regularization cocktail. The regularizers discussed are classified as follows: weight decay, data augmentation (eg. mixup), ensemble (eg. dropout), structural (eg. skip connections), and implicit (eg. BatchNorm). BOHB is used as the HPO method.

**Experiments:** 
The authors lay down three hypotheses and design experiments to validate them. The hypotheses are: 1) cocktails outperform SoTA DL methods on tabular data, 2) cocktails outperform GBDTs on tabular data, and 3) cocktails are tie-efficient. The authors also collect a large benchmark consisting of 40 tabular datasets for diverse classification problems. The authors compare against a strong set of baselines including multiple implementations of GBDTs and recent neural models, all of which are “carefully tuned” on a validation set. They also assess the statistical significance of their results using the Wilcoxon significance test. 

**Comments:**

* Why do we want DL for tabular data? What benefits does it offer over GBDTs? The paper doesn’t talk about this. DL is probably a better fit for automating pipelines and requires less human engineering, but when is this worth the compute and training+inference time overhead?

* Why do GBDTs perform well on tabular data?<d-footnote>See <a href="https://www.reddit.com/r/MachineLearning/comments/9826bt/d_why_is_deep_learning_so_bad_for_tabular_data/">this</a> reddit discussion for more details: https://www.reddit.com/r/MachineLearning/comments/9826bt/d_why_is_deep_learning_so_bad_for_tabular_data/ </d-footnote> Classification can be viewed as carving out decision boundaries in some representation space. Tabular data is often regular (more linearly seperable) than unstructured data (eg. image data). Tree-based models, by virtue of their design, are better at cleanly slicing hyperplanes through data. OTOH, DL creates non-linear boundaries.

* In the experiments, XGBoost is not endowed with feature engineering, thus rendering it weaker than it is in practice. The neural networks are getting attention (in the form of regularization search and tuning), so one may argue about the fairness of this comparison.

