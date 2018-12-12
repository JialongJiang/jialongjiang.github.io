---
title: 'Caltech CMS Lectures Dec'
date: 2018-12-03
permalink: /posts/2018/12/cms_lectures_nov/
tags:
  - notes
---

This month is accompanied by both exams and holidays. Please be kind to me December!

## Decentralized Control over Unreliable Communication Links

## Ashutosh Nayyar, USC	12/03/2018

#### Introduction

Decentralized systems; decision and control problems; decision makers; dynamical environments; information asymmetry; decision of one agent affects other    
Structural difficulties: linear control not optimal, sufficient statistics; computational difficulties  
Decentralized LQG control; system level constraints  
Graphical model for connections; common theme  
Question: inter-controller communication is unreliable  

#### Packet-drop communication 

Two-controller; multi-controller; decentralized control  
Plant dynamics; two controller with unreliable communication  
Quadratic cost function; Finite-horizon decentralized problem; infinite-horizon decentralized control problem  
Common information approach: identifying irrelevant information; formulate equivalent problem, fictitious coordinator knowing the common information; sufficient statistics in the coordinator's problem; dynamic program based solution, structure of the solution   
Linear in state; switch linear 
Infinite: convergence and condition; optimal decentralized  
Auxiliary MJLS problem  
Packet drop probability threshold; 

Multiple local controllers; decentralized control of inter connected subsystems

#### Summary

Finite-horizon: common information; Infinite: connection to MJLSs  
Output feedback; control with unknow dynamics

This talk is very heavy for control theory so I hardly understand the derivation. The author proposed an algorithm to address the issue of unreliable communication. That's all I know about the talk. 

## Reasoning in Bayesian Opinion Exchange Networks is Computationally Hard

### Jan Hazla, MIT	12/04/2018

#### Introduction

Aumann's agreement theorem: common prior and common knowledge posterior cannot agree or disagree; contrary to experience; prior, dishonest, not rational, computational hard  
Rational agents on a network: economics, bounded rationality; rationality as a benchmark; graph structure  
Bayesian opinion exchange; binary state; directed network of agents; u to v: u observes v; dynamics; private signal, independent; each time step, broadcast action; observation history $H$, action by most probable state  
Only action take account; model as common knowledge; honest (myopic); stock market  
Log likelihood by own private signal and actions of neighbors   
Agreement: strongly connected, agents converge to same action; learning: common action equal to true state as number of agents grows; efficient algorithm if sate and signal are Gaussian  

#### Computational Problem

Bayesian computations; binary-action; compute binary action is NP-hard; belief  
Mapping to 3-SAT; size of network; if clauses satisfiable, belief close to 1; if clauses not satisfiable, belief close to 0   
 PSPACE-hard; TQBF 3-CNF  
Reduce formula of 3-SAT to the problem; observer agent, evaluation agent; specify network and history of OBS; counting; choose history satisfying some condition; variable gadget; clause gadget  
TQBF instance (quantified Boolean formula); place intermediate observer solving an NP problem   
Open problems: average case hardness; algorithms; revealed belief model; Gaussian case 

#### Summary

For the problem of Bayesian inference on a graph, the author try to construct special case where the computational complexity is hard. This type of model is widely used in economics and social science. However, the construct of the result might be arbitrary, and it might be more insightful to consider the computational complexity of the average case. 



#### Introduction

Estimation after parameter selection; estimation after model selection  
Not data selection; not testing after selection; not for specific model  
Observation; parameter selection; estimation; cognitive radio communication; medical treatments: several treatment is available, selection bias; Gaussian distribution: estimation $\theta+w$ with noise, select the tail, the estimator is biased , Tweeie's formula  

#### Model

Data generating model; selection rule; estimation  
Naive selection: coin flipping; coin related to parameters, non-Bayesian estimation, nuances parameter; population model with treatment  
Non-Bayesian estimation; Fisher; Lehmann; cost function: MSE; minimum variance unbiased estimation; MSE lower bound; Lehmann-unbiasedness: regard to to cost function used; the closest in the distribution family  
Design cost function: only the error of selected parameters, selection rule predetermined; post selection unbiasedness (PSSE); uniformly distributed; two different parameters; UV estimator Robbins (1988)  
$\Phi$-Cramer-Rao bound; post-selection Fisher information; decoupled parameters; loss of information
$$
J_m(\theta,\Psi)=J|_{\Psi=m}+\nabla^2_\theta\log P(\Psi=m)
$$
PSML estimator; add penalized term; \Phi-efficiency; not unique (as only relevant to selected parameter's); if exists, achieves; low-complexity; decompose into two terms; information  
Hard to compute; stochastic approximation, no need for selection rule; second-best, selected and just not selected  
Binary exponential model; linear correlated Gaussian model; multiple-Gaussian model  
Two-stage model; sample from full population model; half-data for selection and half for estimation, not using all data   
Cognitive radio spectrum after channel kNN selection; multi-armed bandit; data on unselected arms; take data from unselected channels

#### Model selection 

Number of sources; direction of arrival estimation; polynomial regression: number of required degree; sparse vector estimation, nonempty support  
Selection model then do the estimation; MSSE; from bound of MSSE to MSE  
Sparse vector estimation

#### Summary 

Non-Bayesian estimation after parameter selection; performance analysis: unbiased in Lehmann sense, Cramer-Rao bound for Lehmann-unbiased estimator; estimation: efficiency, lower-complexity methods; adaptive sampling: improve estimation by sampling on unselected parameters

The selection after sampling will introduce biases into the estimation. The author propose to use the concept of Lehmann-unbiasedness to address the issue, and make new estimators. 

## Randomized Algorithms for Convex and Non-Convex Optimization

### Mert Pilanci, Stanford	12/06/2018

#### Introduction

Scale of data; deep learning; large scale; complex models  
Question: reduce data volume without losing important information    

#### Sketching

Data matrix $n\times d$ ; $n$ much larger than $d$; batch optimization; combined batch; combined batch  
Least square prediction: design $S$ $m\times d$ sketching matrix (e.g. i.i.d. $\pm 1$); FFT on random diagonal matrix   
If  $m \geq c_0 \mathrm{rank}^*(A)/\epsilon$ effective rank  
How good is the approximation in the sense of solution $x$; lower bound on estimator; information-theoretically impossible  
Optimal algorithm with complexity $O(nd)$; estimation on small batch, compute the residue, second round use the residue as sketching; iterative sketching; optimal prediction in $\log(n/d)$ rounds   
Generalized to arbitrary function; Newton method; affine invariant  
Newton sketch; affine invariant distribution; $C \log(1/\epsilon)$  
Logistic regression; with correlated data; Newton sketch behaves better; Linear programming. interior point  method

#### Distributed Optimization 

ADMM: partition the data; introduce constraints $x_1=x_2​$ with Lagrange multiplier; convergence; minimize communication; naive sampling statuaries  
Randomized direction method of multipliers; DFT matrix with randomly perturbed rows; converge rate $C\log(1/\epsilon)​$  
Non-convex optimization; Gauss-Newton method; compute the Jacobian by back propagation  
Streaming optimization; privacy; distributed and fault tolerant computing; 

#### Summary 

The method of sketching choose better projection direction to reduce the dimension of training data. Sketching basically adjust the projection by the residue, and the idea may have wider application.

## Inference with Covariate-Adaptive Randomization

### Azeem M. Shaikh, UChicago	12/11/2018

#### Introduction 

Random controlled trials; avoid imbalance in baseline covariance; stratified block randomization; implication for inference about average treatment effect; method for i.i.d. data is still valid, but not powerful  
Outcome $Y$, indicator $A$, covariate $Z$; interested in if treatment have effect (different expectation)   

#### Reuslts

Two-sample t-test; permutation test within strata  
Multiple treatment; matched pair  

#### Summary

I totally didn't follow what he was talking about. He was speaking so fast and the slides were with tiny font. The basic idea is, in the context of stratified samples, the estimator for homogenous samples still holds, but not optimal. There are some methods to improve the performance of the estimator. 



