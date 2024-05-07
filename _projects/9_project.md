---
layout: page
title: Bimanual Robot
description: Hardware and software of a 12-DoF cobot with grippers (2022)
img: assets/img/bimanual_cover.png
importance: 3
category: robot
# redirect: https://unsplash.com
---

Based on the previous [robotic project](https://jia-xinyu.github.io/projects/8_project/), we developed a 12-degree-of-freedom (DoF) collaborative robot (**cobot**) in 2022. It has a pair of force-controlled robotic arms, each equipped with a gripper.

Project members: 
* Mechanics: [Terry Cavan Chan](https://cde.nus.edu.sg/bme/bioroboticslab/author/terry-cavan-chan/), <u>Xinyu Jia</u>, [Haotian Guo](https://cde.nus.edu.sg/bme/bioroboticslab/author/guo-haotian/).
* Electronics / Software / Algorithm: <u>Xinyu Jia</u>.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bimanual_cover.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/dual/bimanual_me.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Bimanual robot.
</div>

The robotic arm is mounted on the body with an inclination of **45°** to avoid singularity near frequently used configurations.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/dual/bimanual.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/dual/frame.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Robotic arms.
</div>

We design several sizes of grippers for different scenerios. Their fingers are underactuated and assembled with **tactile sensors**. For more information, please refer to my colleague Haotian Guo's [paper](https://ieeexplore.ieee.org/document/9793603).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/dual/gripper_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/dual/gripper_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Robotic grippers.
</div>

The robot also has eyes (ZED 2 stereo camera) and a 2-DoF neck (DYNAMIXEL MX-106R motor). In fact, the robot has a similar configuration to its [predecessor](https://jia-xinyu.github.io/projects/8_project/) in terms of **electronics** and **software**.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/dual/dual_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/dual/dual_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Bimanual collaborative robot.
</div>

We validate the control algorithm in **CoppeliaSim** simulation and on real hardware. More demo videos are in preparation.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include video.liquid path="assets/video/dual/sim.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include video.liquid path="assets/video/dual/parallel_1.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
</div>
<div class="caption">
    Simulation and hardware experiment.
</div>
