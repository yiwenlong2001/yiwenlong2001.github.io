---
title: Cluster review notes (updating...)
description: One of notes of CS245 
date: 2023-10-26 00:00:00+0000
image: cluster.jpg
tags: 
    - Data analysis
    - UCLA Course Note
    - Cluster
categories:
    - Note
    - UCLA Course
---

# Cluster

## Algorithm_1 K-means

- randomly choose initial cluster centroics.
- assign each point to its nearset centroic.
- do iteration until the location of any centroics does not change:
  - caluculate the mean value for every point of each cluster.
  - relocate every point.

## Algorithm_2 PAM

- Arbitrarily choose k objects as the initial medoids
- Until no change, do 
  - (Re)assign each object to the cluster to which the nearest medoid
  - Randomly select a non-medoid object o’, compute the total cost, S, of swapping medoid o with o’ 
  - If S < 0 then swap o with o’ to form the new set of k medoids

> **Swapping Cost:** Measure whether o’ is better than o as a medoid

## Algorithm_3 CLARA

- random sample in huge data
- do PAM

 > PAM search the whole graph  
 > CLARA search some random sub-graphs

## Algorithm_4 Hierarchical Clustering

 ### AGNES (agglomerative)

- Initially, each object is a cluster
- Step-by-step cluster merging, until all objects form a cluster

 ### DIANA (divisive)

- Initially, all objects are in one cluster
- Step-by-step splitting clusters until each cluster contains only one object

## Algorithm_5 BIRCH

 > Clustering Feature:  CF = (N, LS, SS)  
 > N: #data points  
 > LS: sum of position  
 > SS: sum of the square of the position 

- Phase 1: scan DB to build an initial inmemory CF tree (a multi-level compression of the data that tries to preserve the inherent clustering structure of the data) 
- Phase 2: use an arbitrary clustering algorithm to cluster the leaf nodes of the CF-tree 

## Algorithm_6 Distance-based Methods