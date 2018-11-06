---
title: 'Caltech CMS Lectures Nov'
date: 2018-11-05
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

Quantum information: quantum relative entropy $\textrm{tr}[X(\log{X}-\log(Y))]$   
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
I_{wind}(A) = \int_A^A P_1(x,A)\frac{e^{ikx}}{\sqrt{|x|}}dx
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