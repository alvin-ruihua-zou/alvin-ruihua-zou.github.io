---
title: "Autonomous Vehicle Path Planning & Control"
collection: talks
type: "complete"
permalink: /projects/AV-path-planning-and-control
excerpt: "In this project I created a simulation of AV navigation in a parking lot.<img src='/images/animation_demo.gif' width = '480' height = '480'>"
# venue: "London School of Testing"
# date: 2014-02-01
# location: "London, UK"
---

<!-- [More information here](http://example2.com) -->

Introduction
======
I developed a simulation framework for autonomous vehicle navigation in a parking lot as a class project for 16350 Planning Techniques for Robotics. This included:
- Planning trajectories for the robot considering vehicle dynamics.
- Implementing model predictive control (MPC) for path following under dynamics and environment constraints.

I coded the trajectory generation entirely from scratch in Python and utilized libraries for MPC. I presented the work as a top project in the class.

Planner
======
For trajectory generation, I used an A\* based planner with motion primitives. I first derived simple motions primitives of the vehicle using a unicycle dynamics model, then I used them as the actions space for the vehicle, form a lattice graph in free space. For the planner itself, I used weighted A\*, but I also worked on implementing a version that uses anytime reusable A\* (ARA\*).



<figure style="display: flex; flex-direction: column; align-items: center;">
  <img src="{{site.url}}/images/prims_640x480.png" alt="Motion primitives"/>
  <figcaption>Motion primitives for the vehicle</figcaption>
</figure>

<figure style="display: flex; flex-direction: column; align-items: center;">
  <img src="{{site.url}}/images/animation_demo.gif" alt="Animation"/>
  <figcaption>Animation of a trajectory</figcaption>
</figure>
