---
title: 'Caltech CMS Lectures Nov'
date: 2018-11-02
permalink: /posts/2018/11/cms_lectures_nov/
tags:
  - notes
---

I spent a lot time these days attending seminars in CMS on statistics and algorithms. Some were really inspiring while some I could hardly follow. Therefore I decide to take notes for furture reference, and also to cultivate the habit of writing.

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

Algorithm family $F$, instances $D$  Approach: find good $\hat{A}$ on samples   
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

## Semindefinite Approximation of the Matrix Logarithm 

### Pablo A. Parrilo, MIT	11/05/18

#### Motivation

Quantum information: quantum relative entropy $D(X||Y)=\textrm{tr}[X(\log{X}-\log(Y))]$   
SDP only solve semialgebraic problems, but logarithrms are not   
Approximations, approximation quality, SDP complexity   

#### Logorithm 

Monotone, concave; related: entropy, KL divergence   
Matrix log: apply to eigenvalues; operator monotone, operator concave   
Matrix entropy: concave; quantum ralative entropy: convex   
Use projection to make approximation; semidefinite representation of size $d$   
 Want: size of representation grow mildly   
Matrix arg; bimatrix arg; perspective; NC perspective   
Integral representation

$$
\log x = \int_0^1 \frac{x-1}{1+\xi(x-1)}d\xi
$$

Rational, monotone, concave; SDP representation   
Finite sum approximation $ r_m(x)$; $m$  LMIs of $2\times2$   
Best quadrature: Gauss-Legendre weights; Pade approxation at $1$   
Take exponents down: $r_m(x)$ is good approximation at $x\approx1$   

$$
2^kr_m(x^{1/2^k})
$$

$m+k$ LMIs of $2\times2$  
Optimal choice: $m\approx k$    
Error $\epsilon$, range $[1/a, a]$: $O(\sqrt{-log\epsilon}+\log\log a)$  
Matrix case: $2n\times2n$; Briggs-Pade method; preserves operator concavity; free spectrahedra 

Operator relative entropy cone  
Relative entropy of entanglement   

#### Summary

Matrix logarithm can be approximated by $2n\times2n$ LMIs and thus efficiently solvable by convex optimization solvers.  

## Fast Spectrum Solvers for Computational Science and Engineering

### Oscar Bruno, Caltech	11/05/2018

#### Introduction

Classical local simulation paradigm; Dispersion error is accumulative   
FDTD has to use very fine gird  
Fourier: accuracy; FFT   
Trapezoidal rule; specturm convergence  
Gibbs phenomenon 

#### Method

Slow-rise windowing / Periodic summation    
Fourier continuation


$$
I_{wind}(A) = \int_{-A}^A P_1(x,A)\frac{e^{ikx}}{\sqrt{|x|}}dx
$$

Spectrum convergence by properties of $P_1(x, A)$  
Fourier series of non-periodic function: add extra interval, fourier continuation 

Pure frequencies in time (time harmonic)   
Scatter problem of plane waves 
Polynomial refinement  
Seperate into logical rectangular; Chebyshev rectangular-polar integration  
Waveguide  
Adjoint optimization for integral-equation methods  
Design wave splitter; focus light based on wavelength; micropartical-arrays 

#### Summary

Specific forms of integration equation can be efficiently solved in Fourier space. The problem of Gibbs phenomenon can be solved by using some approximation method. As many applications in physics and engineering require solving integration equation related to harmonic waves, the method is very promising. 

## Off-policy Evaluation and Learning in Theory and in the Wild

### Yuxiang Wang, UCSB	11/06/2018

#### Introduction

Off-policy learning: evaluate algorithm without applying it in real situation  
Contextual bandits model: context; actions; rewards  
Value: expected reward; Data: triplets $(x_i,a_i,r_i)$  
Average treatment estimation: treatment; response variables; covariates  

#### Off-Policy Evaluation

Direct method: fit the model for reward $\hat{r}(x,a)$   
Importance sampling (Horvitz & Thompson, 1952) unbiased, large variance  
Modeifying importance weights; doubly roubust estimator  
Optimality: minimax: IPS is optimal in general; new estimator: SWITCH  
Minimax setup: best possiple worst case in all possible reward distributions  
Assume bound on the first and second moments   
Decompositiom: reward randomness + context randomness  
High variance is required; IPS is asymptotically inefficient  
Additional assumption is needed for better asymptotic efficiency  
Classical nonparametirc estimators requrie exponential sample size  

With an oracle (possibly bad), SWITCH between IPS and oracle estimator: use IPS when  

$$
\frac{\pi(a|x)}{\mu(a|x)}\leq\tau
$$

Error bound for SWITCH: variance from truncated IPS + variance from sampling $X$ + bias from oracle 
Example: multiclass classification data sets

#### Off-Policy Learning

Direct method: without knowing the value of the policy  
Collabrative filtering: regression on results; feature map  
Drawbacks of reward model: unrealiable; large searching space; unknown logging policy
Assumptions: bounded rewards,  
Classification with cross entropy loss; can be interpretated as first order approximation of IPS  
Policy imprevement lower bound   
imitate the policy IML  
Use as regularization; diagonse confounder; collect new data  
Logging policy

#### Summary

Using  the historical data to evaluate the possible rewards of a new policy has wide applications. We can model the reward function or directly learn the policy. The large variance of IPS can be alivated by swithing between IPS and reward-based model. The direct learning methods have the interpretation of IML and can be used to investigate more properties of the model. 

## The Future of Computing Domain-Specific Accelerators

### Bill Daily, Stanford / NVIDIA	11/07/2018

#### Introduction

Fast computing, better algorithms, more data   
Moore's Law is dead: need domain-specific accelerators   
Parallelism with locality; Special data types and operations; Optimized memory; Reduced or Amortized overhead; Algorithm-architecture co-design  
Examples: cell phones: ARM cores; GPUs   
Bioinformatics: doing dynamical programming 37x speedup, 26,000x efficiency

#### Design

**Design by cost: Arithmetic is free (particularly low-precision); Memory is expensive; Communication is prohibitively expensive**  
Local SRAM (KB); On-chip SRAM (MB); LPDDR DRAM(GB)  
Algorithm changes  
Darwin accelerators from Graphmap: Filtration, Alignment  
The first step needs read memory and hard to improve  
Reduce the accuracy of the first step and compensating by the second step, which can be accelerated   
Parallelize; Specialized memory for D-soft bin updates   
GACT Alignment   
On-chip memory D-SOFT  
Cost has a time factor  
Hardware of special data sturcture: static sparse weights; trained quantization   
EIE hardware  

Simple parallelism often beats a "better" algorithm  
Accelerate the whole problem  
Keep generality where possible   
Platform for acceleration  
GPU: high-bandwidth, hierachical memory system; effeicient low-precision computation 

#### Summary

As the speed of CPU gradually stops to increase, task-specific hardware design becomes increaingly important to improve the computational power. Based on analysis of time and energy cost of the computing process, domain-specific hardware can be designed to improve our computational abality significantly. 

## Machine Learning: From Genetics to Gene Editing to Protein Optimization 

### Jennifer Listgarten, UCB	11/14/2018

#### Introduction 

Molecular biology: less data cost, more data  
Statistical genetics; gene editing; rational protein engineering   
Hidden confounding factors 

#### Protein engineering

Predict property from DNA sequence   
Stochastic oracle: trained from sequence to property; reverse: given specific properties to predicted sequence   
Oracle: $P(S|x)$, generative model $p(x|\theta^t)$ VAE, HMM  
Iterative over the generative model to predict good sample   
Entropy method, covariance adaptation   
$\theta$  is in the expectation distirbution: maximize over a lower bound; MC estimates for rare events: cross-entropy methods; anneal a sequence of relaxations  
Design by Adaptive Sampling (DbAS)  
Noise-free, random oracle simulation  
Conditional VAE  

#### Summary

The prediction model of properties can also be used to reverse engineering the samples. The generative model can be itatively updated with the prediction model. 

## Network Centrality as Statistical Inference in Large Networks

### Chee Wei Tan, City University of Hong Kong	11/26/2018

#### Introduction 

The original source of a spreading process  
Fast dynamical process; network topology  
Toy example: the central is the source   
Formulation: initial all good; Susceptible-Infectious (SI) spreading model; each vertex equally likely; each time one infection   
Spreading order to probability; optimization on the MLE; G is a degree regular infinite tree

#### Approaches

Spreading order is constrained by the network topology; probability is the same for all order given the central; just count all ways of spreading; solve by message passing; exponential complexity   
For tree, centroid of graph; $G$ is a finite graph, different orders have different probability; previous results not hold  
Example of a line graph; small vertex infected, the optimal tends to be the origin  
New method  

#### Introduction 

Smart grid; power outage; cascade failing; defend on certain vertices   
Minimize the average number of failure of nodes; quadratic expression of components; number of connected components  
Message passing to compute the centroid  
Only one protection: centroid is the solution; more protection centroid decomposition dynamical programming 

#### Summary 

Network centrality; optimization over statistical problems; reverse engineering  
Reverse: given centrality, what problem does it implicitly solve  
Forward: given inference, how to solve the optimization    
How to combine the approaches from first principle and from data 

There are many problems of network statistical inference are related to the property of "center". These problems are related to the established results in the graph theory, and also make new interpretations of them. 