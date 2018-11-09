---
title: 'Caltech BBE Lectures Nov'
date: 2018-11-08
permalink: /posts/2018/11/bbe_lectures_nov/
tags:
  - notes
---

After starting to make notes on math lectures, I feel it unfair if I didn't give the same respect to my own field. So here it is, lecture notes in computational biology and neuroscience. 

# Lecture Notes

## Population Coding of Hand Movements in the Primate Brain

### Hans Scherberger, OPT German Primate Center	11/08/2018

#### Introduction 

Sensorimotor transformation for grasping   
Coding; decoding; neural  networks  
The fronto-pariental grasping circult: AIP; F5; M1 

#### Methods

Baseline; power grip; precision grip; delayed grasping task  
Different neural action potential with different task type and oriantaion & position of handle  
Cue; memory; movement  
Activities are also mudulated by reward (small, large)  
Hand movement: different objects  
Hand traker 27 degree of freedom; reconstruct the whole trajectories  
Classify different grip types  
AIP: visual feature of objects, shape is more important than size; F5: grasp properties

Decoding; Use Bayesian decoder to infer the object based on neural activities   
Use Kalman filter to predict hand kinetics 

Neural networks; visual freature to muscle dynamics   
Similar behaviours are identified from the neural activities and artificial NN

Hypothesis of neuron coding  
Optimal one-dimensional projections based on different functions  
Neural properties are isotorpic on after the projection   

#### Summary 

AIP: object information; F5: grip type information; M1: movement execution: mixed coding  
Decode from activity: grip type and hand kinematics  
RNN reconstruct the circuit  
Population processing: mixed selectivity; dynamic population code  

Many information can be obtained by recording neural activity while performing tasks. Then these signal can be classified and processed with different conditions. However, actually only a small portion of neurons were recorded from the experiment limitation (possiblely less than 1%). Then the large amount of information retrieved from the small population seems amazing. This property is still under debate. 

## On the Rational Boundedness of Cognitive Control

### Jonathan Cohen, Princeton	11/08/2018

#### Introduction 

Control, repress some movement: Example. scratches; only in human   
Parallel tasks  
Control theory; cybernetics; TOKE model  
Congnitive psychological tradition; qualititive description; limited capacity  
Rescent formalism: expected value; rational meta reasoning; cost-benefit analysis  
Why the capacity is limited? Energy? Structure?   
Multitask: crosstalk; interference  
How do make parallelize and scale with network size   

#### Models

Control over different channels; optimal strategy when nodes have overlap  
Graph with shared representation radically restricts independent parallelism (almost exponential decay)   
Why shared representation: learn faster; generalization  
Color name task: shared representations  
Network representation of multiple tasks  
Single task vs. Multi task leanring: the learning try to capture more dominate representation  
Interactive vs. independent parallelism 

#### Summary

The speaker propose that the difficulty of doing parallel tasks mainly come from the shared representation, which can cause interference. The shared representation come from the basic learning process. The network choose shared representation to capture the dominant features and improve the abality to generalize. However, this causes the network cannot make paraelleize the tasks sharing the representation. When trained to do multiple tasks together, tensor product representation is acquired rather than the shared one as before. 

Comments: what is the trade-off relation between the preformance over multiple tasks and the number of representation allowed?