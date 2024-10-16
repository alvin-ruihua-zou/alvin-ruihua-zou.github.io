---
title: "Stair Climbing Food Delivery Robot"
collection: talks
type: "complete"
permalink: /projects/stair-climbing-robot
# venue: "UC San Francisco, Department of Testing"
# date: 2012-03-01
excerpt: "In this project I built a robot that could deliver food through autonomous navigation and stair climbing."
# location: "San Francisco, California"
---
Details of the project can be found in the following system design and development document.\
[Project System Design and Development Document](http://alvin-ruihua-zou.github.io/files/SDDD.pdf)

Introduction
======
In this project I designed and built a robot with two teammates that could navigate and climb stairs autonomously. The projects is motivated by a problem CMU students face - ordering food on campus can be time consuming. With long wait times and the cost of traveling to and from the dining locations, students become less inclined to get food. Thus, we propose a solution to this problem through using a robot that can pickup and deliver food for students. For this project, we focus on the navigation aspect of the task. I worked mainly on the navigation stack, including path planning, localization and stair detection, as well as the integration of different software.

![Robot](/images/stair-climbing-robot.jpg)


System Description
======
We are building a food delivery robot that specializes in delivering indoors. The robot would need to automatically navigate between locations and climb stairs, given a predetermined, complete map. For our project, we will focus on the stair climbing aspect of the robot. The robot consists of a stair climbing system, a 2-wheel, 2 motor drivetrain with a caster wheel on a rectangular chassis, and a perception system. It will also have an easily accessible container to place food. The stair climbing system contains a frame that can be vertically and horizontally displaced using pulleys, which mimics the movement of taking steps. The perception system consists of a realsense camera that provides stereo and depth images.

Software
======
The robot has two modes of operation, one for navigation on the ground and one for climbing stairs. As such, the system software is designed in such a way to capture this separation. There is a navigation module responsible for navigating the robot on flat ground. It contains a localization planner and motion planner that sends outputs to the navigation controller, which then commands the chassis motors. There is also a stair climbing module responsible for making the robot climb stairs. It contains a stair climbing planner that sends outputs to the stair climbing controller, which then commands the x-axis and z-axis motors. Finally there is a perception module. This module will be responsible for object detection, pose estimation, and stair height estimation. It then sends these outputs to the respective modules, which are then used by the planners. 

Consistent with the idea of two modes of operation, between the navigation module and stair climbing module only one is ever running at a given time. The initiation and termination of the software for each module is controlled by a central computer, which acts as a task manager. The perception module will be running constantly, as the other modules both need its output. It also informs the task manager when to switch between modes of operation.

![Software Architecture Diagram](/images/software-architecture.png)


Path Planning and Localization
======
The path planning procedure for the robot is composed of the following steps. First, using a simple model for the robot a set of motion primitives is precomputed based on a discretization. Then, using these primitives a lattice graph is created from the start to the goal. Finally the path is computed using weighted A*.

For localization we use odometry data collected from the wheel encoders to reinitialize the start state of the robot and then replan.



Stair Detection
======
After an image is captured by the realsense camera, the image is processed by the following steps. 

1. The horizontal edges are extracted from the image.
2. Edges close to each other within some threshold are grouped together.
3. The resulting edges are overlayed on the depth image, segmenting the image.
4. The middle 1/3 of the image is examined, the rest is cropped.
5. Calculate the mean depth of each rectangular segment.
6. Check if the distribution of the mean depth for the segments satisfy the criteria for stairs.
7. Output detection results.

The criteria for stairs is based on the assumption that the each stair step will be farther away from the camera by the same amount. Thus if the distribution of the depths match this pattern it will be likely that the camera has detected stairs. We tested this algorithm on multiple staircases as well as other non staircase objects (e.g hallway), and our algorithm was able to correctly identify stairs with over 95% accuracy.


![Stair Detection Diagram](/images/stair-detection.png)

![Stair Detection Algorithm](/images/stair-detection-algorithm.png)

Demo Video
======

<video src="/video/demo.mp4" width="100%" height="100%" type="video/mp4" controls></video>