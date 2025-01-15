---
layout: page
title: Quadruped Robot
description: Hardware and software of a 12-DoF legged robot (2021)
img: assets/img/legged_cover.jpg
importance: 6
category: robot
related_publications: false
---

I started my Ph.D. at the [NUS Biorobotics Lab](https://cde.nus.edu.sg/bme/bioroboticslab/) on Aug 3rd 2020, focusing on developing novel **motion planning** and **motion control** algorithms. In addition to my research, I also participated in hardware and software development of several robotic platforms.

In the first year, I collaborated with 4 reseach engineers to develop a **quadruped robot** from scratch. Thanks to them, I had a systematic understanding of robots with high degrees of freedom (DoFs).

Project members:
* Mechanical Engineers: Shounak Bhattacharya, <u>Xinyu Jia</u>.
* Electronic Engineers: <u>Xinyu Jia</u>, Sumantra Sharma, Low Chang Hong.
* Software Engineers: <u>Xinyu Jia</u>, Sumantra Sharma, Low Chang Hong.
* Algorithm Engineers: <u>Xinyu Jia</u>, Hari Prasanth Palanivelu.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged_cover.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/legged_me.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    12-DoF quadruped robot.
</div>

It is a **16.5kg**, electrically actuated, torque-controlled, four-legged robot. The leg link can reach **0.5m** when full extended. Most of mechanical components are customized, mainly made of aluminum alloy, carbon fiber, and 3D-printing material. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/leg_2.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/leg_3.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/body_2.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Mechanical design. The figures from left to right illustrate the leg transimission, joint layout, and body structure.
</div>

There are 12 actuated joints in total. Each joint is equipped with a (brushless DC electric) **BLDC motor** (GYEMS RMD X8 Pro). The motor intergates a **6:1 planetary reducer** and a driver that supports 3 control modes (potision / velocity / torque).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/ele_1.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/ele_2.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Electronic system.
</div>

The onboard computers include an Advantech **PC104** and a NVIDIA Jetson **TX2**. The former functions as a low-level motion controller, while the latter runs high-level control and learning algorithms. In terms of sensing, each joint has a **encoder**, and the robot body has a 9-axis inertial measurement unit (**IMU**) (WitMotion HWT901B) for state estimation. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/elec_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/elec_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/plate_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Electronic devices and wiring.
</div>

The robot is powered by a 24V 6000 mAH Li battery. Three voltages are available for electronics: 24V - motors, 12V - computers, 3.3V - LEDs and switches. These devices communicate with each other via different protocols including **CAN**, **UDP** and **USB**.

The robot's real-time software architecture allows code to run in isolated threads, which are bound to different CPUs.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/ele.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/software.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Wiring diagram (left) and software architecture (right).
</div>

We develop the locomotion controller based on the well-known [Mini Cheetah](https://github.com/mit-biomimetics/Cheetah-Software). The hierarchical control framework consists of: 
* a model predictive controller (**MPC**) computing desired body position, body orientation, and foot force in a short horizon.
* a whole-body controller (**WBC**) prioritizing tracking tasks and computing joint position, velocity and torque command.
* several low-level modules processing user instructions or sensor feedback for the high-level controllers. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/control.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Hierarchical control framework.
</div>

The algorithm is verified in **ROS/Gazebo**. The videos below show three robot states: "balanced stand", "stand up", and "trot".

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/legged/balanced_stand.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/legged/trot_sim_all.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
</div>
<div class="caption">
    Simulation in ROS/Gazebo.
</div>

Simultaneously, we conduct single-leg hardware experiments on a bench.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/test_leg_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/test_leg_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Single leg test.
</div>

The completed robot can't wait to run on the ground!

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/close_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/legged/close_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Side view (left) and top view (right).
</div>

We command the quadruped robot to trot indoors and outdoors. Its agile maneuvers demonstrate good locomotion performance.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/legged/trot_in.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
</div>
<div class="caption">
    Trot indoors.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/legged/trot_out.mp4" class="img-fluid rounded z-depth-1" controls=true muted=true autoplay=true loop=true %}
    </div>
</div>
<div class="caption">
    Trot outdoors.
</div>
