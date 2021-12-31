# 6.843-dart-throwing
Dart throwing project for 6.843 (Robotic Manipulation). By Valerie Chen and Gregory Xie.

Most of the development was done in Deepnote, this repository is just a snapshot of the Deepnote project at the time of project submission.
Hopefully this helps someone. 

## What did we do?
In this project, we simulated dart throwing with a Kuka iiwa arm in Drake. This problem is a bit different than just throwing a ball because there are some
additional constraints on how the dart is released. We also implemented rudamentary aerodynamics to better simulate the actual trajectory of the dart. 

We approached the dart throwing problem by splitting it into two halves, finding a release state and generating a trajectory
to take the arm to and from the release state. 

We framed the first half of the problem as an optimization problem, which we could easily solve using the optimization tools provided by Drake. We explored
a couple of different methods to solve the second half of the problem, including RRT* and constant-acceleration trajectories in configuration/task space. Our
approach and results are detailed in the report pdf. 

## But did it work?
Kind of. We were able to generate one arm trajectory that threw the dart succesfully, hitting the dartboard with an error of 9 cm from a distance of 2 meters. 
Most of the trajectories that we generated result in the dart missing the dartboard (too low) or in collisions between the gripper and the dart after release.
Analysis of these problems are also in the report pdf.

**Warning: This code is messy. It is partially commented, but I might clean it up more in the future.**

