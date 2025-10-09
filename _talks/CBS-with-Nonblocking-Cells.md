---
title: "Using Non-Blocking Cells to Improve the Scalability of Conflict Based Search"
collection: talks
type: "complete"
permalink: /projects/CBS-with-nonblocking-cells
excerpt: "Within the spectrum of Multi-Agent Path Finding (MAPF) algorithms, there is often a trade-off between the speed/scalability of the algorithm and the solution optimality/theoretical properties it provides. This work looks at a way of breaking this trade-off through exploiting the properties of the given MAPF instance. The proposed method Decoupled Conflict Based Search (DCBS) identifies a set of non-blocking cells within the graph, assigns priorities to agents based on whether their start/goal states are blocking, and plans agents in groups in descending priority. This effectively decouples the problem into a series of smaller subproblems, which in turn makes the algorithm more scalable while maintaining completeness. Experimental results show that DCBS has faster runtime and better scalability than Priority Based Search and has almost identical solution costs.\n\n<img src='/images/animation_dcbs.gif' width = '300' height = '300'>"
---

Details of the project can be found in the following report.\
[Project Report](http://alvin-ruihua-zou.github.io/files/analog-slp.pdf)

Introduction
======
In this project I designed a framework that dynamically decouples agents into groups with different priorities based on their start/goal locations, and plans agents in groups in descending priority. Through this decoupling, the problems is reduced to smaller subproblems, which effectively makes existing solvers like conflict based search (CBS) more scalable.
