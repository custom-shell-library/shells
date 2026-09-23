# Shell

**Class:** example
**Generation:** 1
**Version:** 0.0.0
**Glossary:** 2026-09
**Condition:** draft
**Author:**
**Last updated:**
**Repository:**

---

## Identity

**Role** — what it does. One sentence.
**Environment** — indoor, outdoor, hazardous, space, aquatic, etc.
**Mission** — inspection, manipulation, transport, exploration, interaction, etc.
**Operator** — who controls it. Single operator, supervised, autonomous.
**Reusability** — one-off, repeatable build, production candidate.

---

## Spec

**Physical** — mass, footprint, height, center of mass, material.
**Kinematic** — DOF, reach, joint limits, max joint velocity.
**Dynamic** — payload, top speed, acceleration, repeatability, accuracy.
**Power** — voltage, capacity (Wh), runtime, charge time, peak draw.
**Thermal** — operating temperature, storage temperature, cooling method.
**Environmental** — IP rating, humidity, vibration tolerance, shock tolerance.

---

## Frame

**Bill of materials** — every part, quantity, source, cost, lead time, Hardware link.
**Structure** — frame material, manufacturing method, tolerances.
**Actuation** — motors, gearboxes, drivers, transmission.
**Locomotion** — wheels, legs, tracks, propellers, or fixed base.
**Manipulation** — arms, hands, grippers, end effectors.
**Power system** — battery, BMS, converters, distribution.
**Wiring** — harness, routing, connectors, strain relief.
**Custom parts** — CAD files, print files, CNC files, drawings.
**Fasteners** — screws, bolts, inserts, adhesives.
**Tools required** — for assembly and maintenance.

---

## Systems

**Manifest** — every package, version, source, license, Software link.
**Firmware** — bootloader, motor firmware, sensor firmware.
**Middleware** — ROS version, RMW, message definitions.
**Perception** — cameras, LiDAR, IMU, fusion stack.
**Control** — low-level loop, controllers, gains.
**Planning** — path, trajectory, task planners.
**Learning** — policy architecture, training framework, dataset format.
**Teleoperation** — input device, mapping, feedback.
**Safety** — limits, watchdogs, e-stop, fail-safe behavior.
**Logging** — format, rate, storage, synchronization.
**Networking** — Wi-Fi, 5G, VPN, remote access.
**Config files** — link to each.
**Launch files** — link to each.
**Dependencies** — external libraries, drivers, toolchains.

---

## Interface

**Emits** — topics, message types, rates.
**Accepts** — topics, message types, rates.
**Serves** — services, request/response types.
**Executes** — actions, goal/feedback/result types.
**Extensions** — namespaced additions beyond the standard contract.
**Frame conventions** — TF tree, base frame, sensor frames.
**Units** — SI, radians, meters, seconds.

---

## Model

**URDF / Xacro** — link.
**SDF** — link, if used for simulation.
**Calibration** — encoder offsets, IMU bias, camera intrinsics/extrinsics, joint zeros. Date performed.
**Dynamics** — masses, inertias, friction, damping, identified actuator gains.
**Sensor transforms** — mount positions and orientations.
**Collision geometry** — simplified shapes, margins.
**Visual geometry** — meshes, textures.

---

## Trials

**Bench** — motor tests, sensor tests, power tests. Pass/fail, measured values, date.
**Integration** — middleware bring-up, teleop latency, logging integrity. Pass/fail, measured values, date.
**Field** — task performance, failure modes, safety validation. Pass/fail, measured values, date.
**Endurance** — continuous run duration, degradation observed.
**Environmental** — tested temperature, humidity, vibration, shock.
**Known limitations** — what it cannot do yet.

---

## Log

**Build history** — dated entries, what changed, why.
**Open issues** — links, priority, status.
**Changelog** — version bumps, what triggered each.
**Lessons learned** — what would be done differently.
**Cost actual** — final spend vs. BOM estimate.

---

## Status

**Condition** — draft, building, operational, learning, autonomous, deprecated.
**Blockers** — what is preventing progress.
**Next steps** — what happens next on this Shell.
