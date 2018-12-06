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