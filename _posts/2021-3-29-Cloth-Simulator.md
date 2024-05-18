---
layout: post
title: Cloth Simulator
---

I simulated a cloth that consists of mass nodes connected by springs and dampers. The goal was to explore the effect of different stiffness and damping settings on simulation speed, simulation stability, and cloth appearance.

**Mass-Spring Model**:

The Mass-Spring Model is a very basic method to simulate cloth. It is relatively easy to implement. The cloth is simulated as a grid of particles, which are connected to each other by spring-dampers. Each spring-damper connects two particles and generates a force based on the particles' positions and velocities. We will use three types of spring dampers that are
shown below: stretch springs (also known as structural springs), shear springs, and bend springs. In addition to these spring forces, each particle is also influenced by gravity. The layout of this model is illustrated in the figure below:

![Springs]({{ site.baseurl }}/images/cloth_springs.png)


The next piece I wanted to experiment with was different integration techniques to observe changes in simulation speed and stability. I implemented Euler, Verlet, and Semi-implicit integrators.


This is a [link](https://github.com/vaishmantha/15464-miniproject2) to my implementation. You can see different video captures in this repo.

![ExampleCloth]({{ site.baseurl }}/images/cloth_demo.gif)



