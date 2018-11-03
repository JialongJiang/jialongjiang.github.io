---
title: 'Caltech CMS Lectures Nov'
date: 2018-11-02
permalink: /posts/2018/09/cms_lectures_nov/
tags:
  - notes
---

I'll start to post notes on the lectures in Caltech CMS.

# Lecture Notes

## Data Driven Algorithm Design

### Maria-Florina Balcan, CMU	11/02/18

#### Introduction

Classical: worst case; most domains are hard

Data driven: leaning & data 

From empirical to formal guarantees

#### Clustering

Objective-based: k-means, k-median, k-center (minimax radius) 

NP-hard

#### Sampling complexity of algorithms selection

Algorithm family $F$, instances $D$. 

Approach: find good $\hat{A}$ on samples

Question: how many instances are required to make the performance on training set effective in all $D$  

Uniform convergence; $N=O(\textrm{dim}(F)/\epsilon^2)$ for $\epsilon$-close instances

VC-dimension 

Clustering: Linkage Dynamic programming

Use different distance for hierarchical clustering to build the linkage tree

Complexity of the linear interpolation is $O(\log(n))$  

Partitioning by IQPs

Data driven mechanism design

#### Summary 

One special property of machine learning problem is that what we care about is the hidden dataset rather than the observed samples, which is always denoted as the generaliation abality of the algorithm. The theory of uniform convergence could help us to establish such a relation between the performance on the training set and all possible samples. The requirement of $\epsilon$-separability are widely used in establishing bounds of best possible estimators.  