---
title: PyTorch CUDA Operators Parallelism Implementation and Optimization
description: SJTU course project
date: 2023-12-25 00:00:00+0000
image: GPU.jpg
tags: 
    - C/CPP
    - Pytorch
    - CUDA
    - Algoritm
categories:
    - Project
weight: 4
---

- Employed warp-level primitives to optimize warp reduce of Softmax Kernel, which improved efficiency by 7%
- Implemented matrix multiplication kernel with matrix chunking and shared memory in C and CUDA
- Optimized shared memory access via vector read instruction LDS.128, resulting in a 3% efficiency improvement
[<span style="color:blue"> Github Repo Link <span>](https://github.com/wangshanyw/PyTorch-CUDA-Operators-Implementation-and-Optimization)
[<span style="color:blue"> Docs Link <span>](https://docs.google.com/presentation/d/1uhkq8XJ8SvoxHUiech5nn_noU7b2TYk7/edit?usp=sharing&ouid=108660935975018643927&rtpof=true&sd=true)
