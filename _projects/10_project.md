---
layout: page
title: Quadruped Manipulator
description: Hardware and software of a 18-DoF mobile manipulator (2023)
img: assets/img/legged_arm_cover.png
importance: 4
category: robot
---

In 2023, my third year at the NUS, I participated in the development of a 18-degree-of-freedom (DoF) **quadruped mobile manipulator** robot. It consists of a 12-DoF [legged robot](https://jia-xinyu.github.io/projects/7_project/) and a 6-DoF [robotic manipulator](https://jia-xinyu.github.io/projects/8_project/), expected to perform mobile manipulation in complex terrain.

Project members: 
* Mechanics: [Terry Cavan Chan](https://cde.nus.edu.sg/bme/bioroboticslab/author/terry-cavan-chan/), <u>Xinyu Jia</u>.
* Electronics / Software / Algorithm: <u>Xinyu Jia</u>.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm_cover.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/legged_arm_me.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Quadruped mobile manipulator.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/legged.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/arm.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Quadruped robot + Robotic manipulator.
</div>

Compared to its predecessors, the mechanical system has major upgrades. For example, more carbon fiber material is used for lightweighting (**25kg** in total). We also select a more powerful motor (GYEMS RMD X8 Pro 9:1) and design a new leg tranmission structure to support a higher payload.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/frame.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/leg.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Robot body (left) and leg tranmission (right).
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/board.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/bracket.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Simulations of equivalent stress and total deformation.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/joint_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/joint_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Joint connection.
</div>

The electronic system is also upgraded. The onboard computers, PC104 and NVIDIA TX2 in the [previous version](https://jia-xinyu.github.io/projects/7_project/), are replaced by **Intel NUC** and **NVIDIA Xavier**, respectively. The layout of electronic devices is carefully designed to facilitate maintenance after experiments.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/ele_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/ele_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Layout of electronic devices.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/elec_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/elec_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/elec_3.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Electronic system.
</div>

Currently, all hardware has been completed. 
A whole-body planning and control algorithm is being developed to coordinate its **locomotion** and **manipulation**. Let's wait and see!

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/robot_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Close-up view.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_arm/all.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A family photo of my robot friends during my 4-year Ph.D. journey
</div>