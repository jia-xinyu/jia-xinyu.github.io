---
layout: page
title: Pendulum Plaform
description: Hardware and software of a 1-DoF pendulum (2022)
img: assets/img/pendulum_cover.jpg
importance: 5
category: robot
---

For preliminary algorithm verification, we developed a pendulum platform in 2022. It has only one actuated joint equipped a (brushless DC electric) **BLDC motor** (GYEMS L5010) and a **50:1 harmonic reducer**. The electronics is same as in the [robotic manipulator](https://jia-xinyu.github.io/projects/8_project/).

Project members: 
* Mechanics: [Terry Cavan Chan](https://cde.nus.edu.sg/bme/bioroboticslab/author/terry-cavan-chan/), <u>Xinyu Jia</u>.
* Electronics / Software / Algorithm: <u>Xinyu Jia</u>.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/pendulum_cover.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/motor/single.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Pendulum plaform.
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/motor/X8Pro.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/motor/L7010-23T.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Test motor torque constant (roughly).
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/motor/5015_sin.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/motor/5015_5kg_slow.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/motor/5015_gravity_5kg.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
</div>
<div class="caption">
    Free-space tracking, zero gravity mode, max payload test (from left to right).
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/motor/sim_result.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Actuator.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/motor/USDE_step.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/motor/PD_step.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/motor/USDE_step.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Step signal. PD (left) and USDE (right).
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/motor/USDE_sin.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/motor/PD_sin.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/motor/USDE_sin.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Sine signal. PD (left) and USDE (right).
</div>
