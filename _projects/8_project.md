---
layout: page
title: Robotic Manipulator
description: Hardware and software of a 6-DoF robotic arm (2022)
img: assets/img/arm_cover.png
importance: 2
category: robot
# giscus_comments: true
---

In my second year at the NUS, I was responsible for developing a cooperative robotic manipulator. It has the following **features**:
* 3.5kg weight
* 1kg payload @ 0.6m full extension
* 6 degrees of freedom (DoFs)
* joint control modes (position/velocity/torque)
* full robot dynamic model
* physical human-robot interation (pHRI)

Project members: 
* Mechanics: [Terry Cavan Chan](https://cde.nus.edu.sg/bme/bioroboticslab/author/terry-cavan-chan/), <u>Xinyu Jia</u>, [Haotian Guo](https://cde.nus.edu.sg/bme/bioroboticslab/author/guo-haotian/).
* Electronics: <u>Xinyu Jia</u>, [Low Chang Hong](https://cde.nus.edu.sg/bme/bioroboticslab/author/low-chang-hong/).
* Software & Algorithm: <u>Xinyu Jia</u>.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm_cover.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/arm_me.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    6-DoF robotic manipulator.
</div>

As the core component, the actuator is a (brushless DC electric) **BLDC motor** (GYEMS L5010 or L5015) in series with a **50:1 harmonic reducer**. The other mechanical components are customized, made of aluminum alloy, carbon fiber, or 3D-printing material. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/actuator.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Explosive view of the actuator.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/motor_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/arm/motor.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
</div>
<div class="caption">
    50:1 harmonic reducer.
</div>

The robot assembly looks so exquisite!

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/arm_gripper_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/arm_gripper_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/arm_gripper_3.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Full view.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/arm_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/arm_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/arm_3.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Close-up view.
</div>

Regarding its electronics, we design a two-layer PCB board for **Tennsy 4.1** that handles data from different devices.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/board_1.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/board_3.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/board_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Customized PCB board.
</div>

In fact, the robot shares the same electronics as our [bimanual cobot](https://jia-xinyu.github.io/projects/9_project/): an **Intel NUC** computer, Tennsy 4.1 microcontrollers, etc.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/ele_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/ele_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Electronic devices and wiring.
</div>

In addition, we develop a **real-time software** architecture where code can run in different threads under strict time constraints. Excitingly, the low-level code for the Tennsy 4.1 has been **open-sourced**. Please see the [repository](https://github.com/jia-xinyu/Caracal_Teensy).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/software.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Real-time software architecture.
</div>

The robot has a hybrid **force and motion control** framework. It support compliant physical interaction, while can also follow trajectory in joint space or Catersian space. As the dynamics is available, the robot can **detect unexpected collisions** using only proprioceptive data, thus ensuring the safety of humans and itself. Furthermore, we design a finite state machine (**FSM**) to manage different robot states.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/FSM.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/arm/control.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    FSM (left) and control framework (right).
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/arm/sim_circle.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true loop=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/arm/sim_line.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true loop=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/arm/pos.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true loop=true %}
    </div>
</div>
<div class="caption">
    Trajectory tracking in Catersian space.
</div>

Simulation in **CoppeliaSim** validates the effectiveness of the algorithm. Hardware experiments are also conducted for verification.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/arm/sim.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/arm/standup.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/arm/cubic.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
</div>
<div class="caption">
    Hardware experiments.
</div>