## Shell-a1<br>
<br>
Class: arm<br>
Generation: 1<br>
Version: 0.0.0<br>
Glossary: 2026-09<br>
Condition: draft<br>
<br>
Author:<br>
Last updated:<br>
Repository:<br>

---

## Identity<br>
<br>
Role — what it does. One sentence.<br>
Environment — indoor, outdoor, hazardous, space, aquatic, etc.<br>
Mission — inspection, manipulation, transport, exploration, interaction, etc.<br>
Operator — who controls it. Single operator, supervised, autonomous.<br>
Reusability — one-off, repeatable build, production candidate.<br>

---

## Spec<br>
<br>
Physical — mass, footprint, height, center of mass, material.<br>
Kinematic — DOF, reach, joint limits, max joint velocity.<br>
Dynamic — payload, top speed, acceleration, repeatability, accuracy.<br>
Power — voltage, capacity (Wh), runtime, charge time, peak draw.<br>
Thermal — operating temperature, storage temperature, cooling method.<br>
Environmental — IP rating, humidity, vibration tolerance, shock tolerance.<br>

---

## Frame<br>
<br>
Bill of materials — every part, quantity, source, cost, lead time, Hardware link.<br>
Structure — frame material, manufacturing method, tolerances.<br>
Actuation — motors, gearboxes, drivers, transmission.<br>
Locomotion — wheels, legs, tracks, propellers, or fixed base.<br>
Manipulation — arms, hands, grippers, end effectors.<br>
Power system — battery, BMS, converters, distribution.<br>
Wiring — harness, routing, connectors, strain relief.<br>
Custom parts — CAD files, print files, CNC files, drawings.<br>
Fasteners — screws, bolts, inserts, adhesives.<br>
Tools required — for assembly and maintenance.<br>

---

## Systems<br>
<br>
Manifest — every package, version, source, license, Software link.<br>
Firmware — bootloader, motor firmware, sensor firmware.<br>
Middleware — ROS version, RMW, message definitions.<br>
Perception — cameras, LiDAR, IMU, fusion stack.<br>
Control — low-level loop, controllers, gains.<br>
Planning — path, trajectory, task planners.<br>
Learning — policy architecture, training framework, dataset format.<br>
Teleoperation — input device, mapping, feedback.<br>
Safety — limits, watchdogs, e-stop, fail-safe behavior.<br>
Logging — format, rate, storage, synchronization.<br>
Networking — Wi-Fi, 5G, VPN, remote access.<br>
Config files — link to each.<br>
Launch files — link to each.<br>
Dependencies — external libraries, drivers, toolchains.<br>

---

## Interface<br>
<br>
Emits — topics, message types, rates.<br>
Accepts — topics, message types, rates.<br>
Serves — services, request/response types.<br>
Executes — actions, goal/feedback/result types.<br>
Extensions — namespaced additions beyond the standard contract.<br>
Frame conventions — TF tree, base frame, sensor frames.<br>
Units — SI, radians, meters, seconds.<br>

---

## Model<br>
<br>
URDF / Xacro — link.<br>
SDF — link, if used for simulation.<br>
Calibration — encoder offsets, IMU bias, camera intrinsics/extrinsics, joint zeros. Date performed.<br>
Dynamics — masses, inertias, friction, damping, identified actuator gains.<br>
Sensor transforms — mount positions and orientations.<br>
Collision geometry — simplified shapes, margins.<br>
Visual geometry — meshes, textures.<br>

---

## Trials<br>
<br>
Bench — motor tests, sensor tests, power tests. Pass/fail, measured values, date.<br>
Integration — middleware bring-up, teleop latency, logging integrity. Pass/fail, measured values, date.<br>
Field — task performance, failure modes, safety validation. Pass/fail, measured values, date.<br>
Endurance — continuous run duration, degradation observed.<br>
Environmental — tested temperature, humidity, vibration, shock.<br>
Known limitations — what it cannot do yet.<br>

---

## Log<br>
<br>
Build history — dated entries, what changed, why.<br>
Open issues — links, priority, status.<br>
Changelog — version bumps, what triggered each.<br>
Lessons learned — what would be done differently.<br>
Cost actual — final spend vs. BOM estimate.<br>

---

## Status<br>
<br>
Condition — draft, building, operational, learning, autonomous, deprecated.<br>
Blockers — what is preventing progress.<br>
Next steps — what happens next on this Shell.<br>
