# hive

**Class:** swarm<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Centimetre-scale autonomous swarm robot for collective behaviour research. Each unit is a 33 mm diameter, 34 mm tall differential-drive robot with infrared communication, phototaxis sensing, and vibration-based locomotion. A swarm of 10–1000 units exhibits collective behaviours — aggregation, dispersion, formation, collective transport, and self-assembly — that emerge from local rules without centralised control. The platform is a direct descendant of the Harvard Kilobot and the open-source Zuri swarm robot, both of which demonstrated that complex collective behaviour can emerge from extremely simple hardware.<br>

**Environment** — Indoor, flat surfaces only. Tabletop, laboratory floor, or a dedicated arena with a uniform surface. Not for outdoor, uneven, or wet surfaces. Operating temperature 10–35 °C. The swarm requires a controlled arena with consistent lighting and a smooth, non-reflective surface for reliable IR communication and vibration locomotion.<br>

**Mission** — Provide a low-cost, reproducible swarm robotics platform for research into collective behaviour, distributed algorithms, and self-organising systems. The platform supports: (1) Aggregation and dispersion, (2) Formation control, (3) Collective transport, (4) Self-assembly, (5) Synchronisation, and (6) Distributed sensing. Each unit is autonomous; there is no central controller. The swarm's behaviour emerges from local interactions between neighbouring units.<br>

**Operator** — Single operator via an overhead IR controller or a base station connected to a host PC. The operator sets global parameters (e.g., "aggregate", "disperse", "form a line") and the swarm executes the behaviour through local rules. Individual units can also be programmed via IR or USB.<br>

**Reusability** — Fully open-source design. Based on the Harvard Kilobot (open-source, 3.3 cm diameter, vibration motors, IR communication) and the Zuri swarm robot (open-source, modular, 4 cm, magnetic wheels). Repeatable build from off-the-shelf and 3D-printed components.

---

## Spec

**Physical** — 33 mm diameter, 34 mm height. Mass ~12 g including battery (Kilobot: 11 g with battery, 3.3 cm diameter, 3.4 cm height). 3D-printed PA12 or PETG body shell. Two vibration motors for locomotion. IR transmitter and receiver for communication and distance sensing. Phototaxis sensor for light gradient detection. 3.3V lithium polymer battery (100 mAh, 3.7V nominal). The body is a two-layer PCB sandwich with the battery between the layers, following the Kilobot architecture. The Zuri design uses a modular approach with magnetic wheels and a 4 cm diameter, but the vibration-motor approach is simpler and more robust for large swarms.<br>

**Kinematic** — Differential drive via two vibration motors. No wheels; locomotion is achieved by the asymmetric vibration of two unbalanced motors. The vibration motors are mounted on opposite sides of the body and driven at different amplitudes or frequencies to steer. This is not a precise locomotion method — it is noisy, stochastic, and slow — but it is extremely simple, robust, and cheap, which is why it is used in swarm robotics. The Kilobot moves at approximately 1 cm/s. Turning is achieved by driving one motor faster than the other. The robot cannot move in a straight line precisely; its motion is a random walk with a bias determined by the differential motor speeds. This stochasticity is a feature, not a bug: it encourages exploration and makes the swarm robust to individual unit failures.<br>

**Dynamic** — Speed ~1 cm/s (Kilobot: 1 cm/s). Turning rate: differential vibration. Battery life: 3 hours continuous operation (Kilobot: 3 hours with 100 mAh LiPo). Runtime is dominated by IR communication and vibration motor current draw. The robot can operate for ~1 hour in continuous communication mode and ~3 hours in idle mode. The vibration motors draw ~20 mA each at full power; the IR LEDs draw ~20 mA when transmitting; the microcontroller draws ~5 mA active. The battery is 100 mAh, so continuous full-power operation would drain it in under 2 hours. Real-world runtime is 1–3 hours depending on the swarm algorithm and communication frequency.<br>

**Power** — 3.3V lithium polymer battery (100 mAh, 3.7V nominal). Charging via USB or a charging dock. The Kilobot uses a 3.3V LiPo with a custom charging circuit. The Zuri uses a similar battery. Power management: the microcontroller sleeps between communication events to extend battery life. The IR LEDs are pulsed, not continuously on. The vibration motors are driven with PWM to control speed. Total average current draw: ~30 mA active, ~5 mA idle. XT30 or JST connector for battery. 3.3V regulated output for the microcontroller and sensors.<br>

**Thermal** — 10–35 °C operating. Passive cooling. No active thermal management. The vibration motors and IR LEDs generate negligible heat. The microcontroller and battery are the primary heat sources, and they are well within thermal limits at these power levels.<br>

**Environmental** — Indoor, flat surfaces only. Not for outdoor, uneven, or wet surfaces. The IR communication requires a non-reflective surface and consistent ambient lighting. Direct sunlight saturates the IR receiver; the swarm should operate under controlled indoor lighting. The vibration locomotion requires a smooth surface; carpet or rough surfaces impede motion.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost per unit ≈ $15–$30, or $150–$300 for a swarm of 10, $1,500–$3,000 for a swarm of 100.<br>

**Structure** — Two-layer PCB sandwich. The bottom PCB holds the vibration motors, IR receiver, and phototaxis sensor. The top PCB holds the microcontroller, IR transmitter, and charging circuit. The battery sits between the two PCBs. The body shell is 3D-printed PA12 or PETG and clips around the PCB sandwich. The Kilobot uses a custom PCB as the structural element — the board itself is the chassis. This is the most efficient approach for a centimetre-scale robot: the PCB provides both the electronics and the structure, eliminating the need for a separate chassis. The Zuri uses a modular 3D-printed chassis with magnetic wheels, but the Kilobot PCB-sandwich approach is simpler and more cost-effective for large swarms.<br>

**Actuation** — 2× vibration motors. Selected motor: 3V coin vibration motor (10 mm diameter, 3 mm thick, 20 mA, 12,000 RPM). These are the same type of motors used in mobile phone vibration alerts. They are extremely cheap (~$1 each), robust, and draw very little current. The motors are mounted on opposite sides of the PCB sandwich with their vibration axes oriented to produce forward motion when driven equally and turning when driven differentially. The vibration motors are not precision actuators — they are stochastic — but this is acceptable for swarm robotics, where individual unit precision is less important than collective robustness. The Kilobot uses two vibration motors; the Zuri uses two magnetic wheels with differential drive. The vibration motor approach is simpler and more robust for large swarms.<br>

**Locomotion** — Vibration-based differential drive. The two vibration motors are driven with PWM signals from the microcontroller. When both motors run at the same speed, the robot moves forward (with some random deviation). When one motor runs faster than the other, the robot turns. When both motors run at the same speed but in opposite directions (or with asymmetric vibration), the robot can rotate in place. The locomotion is noisy and imprecise; the robot's path is a biased random walk. This is characteristic of vibration-driven swarm robots and is well-suited to collective behaviour research, where the swarm's behaviour emerges from the statistics of many individual random walks.<br>

**Manipulation** — None. The base swarm unit has no manipulation capability. Optional: a passive gripper or a magnetic attachment for collective transport experiments. The Kilobot can push objects or other Kilobots; the Zuri can attach to objects with magnets. For collective transport research, a passive gripper or a sticky foot can be added.<br>

**Power system** — 3.3V LiPo 100 mAh. JST connector. 3.3V LDO regulator for the microcontroller and sensors. The vibration motors run directly from the battery voltage (3.7V nominal, 3.0–4.2V range). The IR LEDs run from a 3.3V rail with current-limiting resistors. Charging via a USB charging circuit (TP4056 or equivalent) or a custom charging dock. The Kilobot uses a charging pad; individual units are placed on the pad and charged via exposed contacts on the bottom PCB. This is the preferred approach for large swarms: a charging pad can charge 100 units simultaneously.<br>

**Wiring** — Minimal. The PCB sandwich eliminates most wiring. The vibration motors are soldered directly to the bottom PCB. The IR LEDs and phototransistors are soldered to the PCBs. The battery connects via a JST connector. The charging contacts are exposed pads on the bottom PCB. This minimalist wiring is essential for a centimetre-scale robot; there is no space for connectors or cable management.<br>

**Custom parts** — 3D-printed body shell (PA12 or PETG). Custom PCB (two-layer, 33 mm diameter). The PCB design is open-source and can be fabricated by JLCPCB, PCBWay, or any PCB manufacturer. The total PCB cost for 100 units is approximately $100–$200, depending on quantity and manufacturer. The 3D-printed shell is optional; the Kilobot uses the PCB as the structural element without a separate shell.<br>

**Fasteners** — None. The PCB sandwich is held together by the battery and the press-fit of the 3D-printed shell (if used). The vibration motors are soldered directly to the PCB. This is a fastener-free design, which is essential for a centimetre-scale robot.<br>

**Tools required** — Soldering iron (fine tip, 0.5 mm), reflow oven or hot plate (for SMD components), multimeter, USB programmer (for the microcontroller), 3D printer (if using a printed shell). For large swarms, a pick-and-place machine is recommended for PCB assembly, but hand assembly is feasible for small batches.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| Microcontroller (ATmega328P or similar) | 1 | Microchip / Digikey | ~$2 | Compute/MCU |
| 3V coin vibration motor, 10 mm | 2 | Various | ~$1 each | Actuators/Vibration |
| IR LED (transmitter) | 1 | Vishay / Digikey | ~$0.50 | Comms/IR |
| IR phototransistor (receiver) | 1 | Vishay / Digikey | ~$0.50 | Sensors/IR |
| Phototaxis sensor (photodiode or LDR) | 1 | Various | ~$0.50 | Sensors/Phototaxis |
| 3.3V LiPo 100 mAh | 1 | Various | ~$5 | Power/battery |
| 3.3V LDO regulator | 1 | Various | ~$0.50 | Power/regulator |
| Charging circuit (TP4056 or equivalent) | 1 | Various | ~$0.50 | Power/charging |
| Custom PCB (two-layer, 33 mm diameter) | 1 | JLCPCB / PCBWay | ~$2 (at 100 units) | Structure/PCB |
| 3D-printed body shell (optional) | 1 | Local print | ~$0.50 | Structure/Shell |
| Passive components (resistors, capacitors) | assorted | Digikey | ~$1 | Electronics |
| Programming header | 1 | Various | ~$0.50 | Compute/Programming |
| **Total per unit** | | | **~$15–$30** | |

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| Overhead IR controller (for programming and control) | 1 | Custom | ~$100 | Operator/Controller |
| Charging pad (for 100 units) | 1 | Custom | ~$200 | Power/Charging |
| Host PC (for swarm control) | 1 | Various | ~$800 | Compute/PC |
| Arena (flat surface, 1–2 m²) | 1 | Custom | ~$200 | Environment/Arena |

---

## Systems

**Manifest** — See detailed manifest below.<br>

**Firmware** — The ATmega328P runs the swarm algorithm. The Kilobot firmware is open-source and available on GitHub. The firmware implements: (1) IR communication protocol (message encoding, transmission, reception), (2) Vibration motor control (PWM), (3) Phototaxis sensing, (4) Swarm algorithm (aggregation, dispersion, formation, etc.), and (5) Power management (sleep modes). The firmware is written in C and compiled with AVR-GCC. The microcontroller runs at 8 MHz and has 32 KB Flash, 2 KB SRAM, and 1 KB EEPROM. The Kilobot firmware fits comfortably within these constraints. The Zuri uses a similar microcontroller and firmware architecture.<br>

**Middleware** — No middleware. The swarm units communicate directly via IR. The overhead controller communicates with the swarm via IR. There is no ROS, no DDS, no MAVLink. The simplicity of the communication is a feature: it enables a swarm of 1000 units to operate without the overhead of a full robotics middleware stack. For integration with a host PC, the overhead controller connects via USB and provides a simple serial or Python API for sending commands and receiving swarm state.<br>

**Perception** — IR receiver for communication and distance sensing. The IR receiver measures the intensity of received IR signals, which is used to estimate the distance to neighbouring units (closer units produce stronger signals). This is the primary sensing modality for swarm algorithms. Phototaxis sensor (photodiode or LDR) for light gradient detection. The phototaxis sensor is used for aggregation experiments and for orienting the swarm relative to a light source. The Kilobot uses a single phototaxis sensor; the Zuri uses multiple sensors for better direction estimation. No camera, no LiDAR, no IMU. The swarm unit is deliberately sensor-minimal to keep the cost and complexity low.<br>

**Control** — The ATmega328P runs the swarm algorithm at 1–10 Hz. The algorithm is a set of local rules that each unit follows based on its own state and the states of its neighbours (received via IR). There is no central controller. The swarm's behaviour emerges from the interactions of many units. Example algorithms: (1) **Aggregation**: each unit moves toward the centroid of its neighbours. (2) **Dispersion**: each unit moves away from its neighbours when too close. (3) **Formation**: each unit maintains a target distance and bearing relative to its neighbours. (4) **Collective transport**: multiple units attach to an object and move it cooperatively. (5) **Synchronisation**: units adjust their internal oscillators to match their neighbours. The Kilobot has demonstrated all of these behaviours. The Zuri has demonstrated magnetic wheel-based collective behaviours.<br>

**Planning** — No global planning. The swarm behaviour is a reactive, distributed algorithm. There is no path planning, no trajectory optimisation, no task allocation. The swarm's "plan" is the emergent result of local interactions. This is the defining characteristic of swarm robotics: global behaviour from local rules.<br>

**Learning** — None in the base platform. The swarm algorithms are hand-designed, not learned. Optional: evolutionary robotics approaches where the local rules are evolved using a genetic algorithm. Optional: reinforcement learning for individual unit policies, though this is computationally expensive for a centimetre-scale robot with an 8-bit microcontroller. The Kilobot has been used for evolutionary robotics research, where the local rules are encoded as a finite state machine and evolved over generations.<br>

**Teleoperation** — The overhead IR controller is used to program the swarm and to send global commands (e.g., "aggregate", "disperse"). The controller is not a teleoperation device in the traditional sense; it does not control individual units. It broadcasts a command to all units in range, and each unit responds according to its local rules. The host PC connects to the overhead controller via USB and provides a Python API for sending commands and receiving swarm state. The Kilobot's overhead controller (the "Kilobot Controller") is an open-source design that can be built for approximately $100.<br>

**Safety** — No safety systems. The swarm units are centimetre-scale, weigh 12 g, and move at 1 cm/s. They cannot injure a human or damage property. The battery is a small LiPo (100 mAh) with a low risk of fire. The vibration motors are low-power. The IR LEDs are Class 1 eye-safe. There is no emergency stop; the swarm can be stopped by removing power or by sending a "stop" command via the overhead controller.<br>

**Logging** — Each unit can log its state (position estimate, neighbour count, algorithm state) to its EEPROM or transmit it via IR to the overhead controller. The overhead controller can log swarm state to the host PC. For large swarms, individual unit logging is limited by the EEPROM size (1 KB) and the IR bandwidth. The Kilobot's IR communication operates at 9600 bps; logging 100 units' state at 1 Hz requires approximately 1 kbps, which is within the IR bandwidth. The Zuri uses a similar approach.<br>

**Networking** — IR communication, 9600 bps, range ~10 cm (Kilobot: 10 cm). The IR transmitter is a single LED; the IR receiver is a phototransistor. The communication is directional; the Kilobot's IR LED is mounted on top of the robot, and the receiver is on the bottom, so communication is primarily with neighbours at similar heights. The Zuri uses a similar IR communication scheme. There is no Wi-Fi, no Bluetooth, no radio. The swarm's communication is entirely local and entirely IR.<br>

**Config files** — The swarm algorithm is compiled into the firmware. There are no runtime config files. Parameters (e.g., target distance, aggregation radius) are defined as constants in the firmware and can be changed by recompiling. The overhead controller provides a simple command interface for selecting algorithms.<br>

**Launch files** — None. The firmware is flashed to each unit via IR programming (the Kilobot's overhead controller programs all units simultaneously via IR) or via a USB programmer (for individual units).<br>

**Dependencies** — AVR-GCC for firmware compilation. AVRDUDE for flashing. Python for the host PC interface. Optional: a simulation environment (e.g., ARGoS, Stage, or a custom simulator) for testing swarm algorithms before deploying to hardware.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| AVR-GCC | Latest | gcc.gnu.org | Firmware/Compiler |
| AVRDUDE | Latest | avrdude | Firmware/Flashing |
| Python | 3.x | python.org | Host PC |
| PySerial | Latest | pyserial | Host PC/Serial |
| ARGoS (optional) | Latest | argos-sim.info | Simulation/Swarm |
| Stage (optional) | Latest | github | Simulation/Swarm |

---

## Interface

**Emits** — IR messages to neighbouring units. The message format is defined by the swarm algorithm. Typical messages include: unit ID, position estimate, neighbour count, algorithm state, and timestamp. The Kilobot's IR protocol uses a 3-byte message (ID, distance, payload). The Zuri uses a similar protocol.<br>

**Accepts** — IR messages from neighbouring units. Commands from the overhead controller (broadcast to all units). USB commands (for individual units).<br>

**Serves** — No services. The swarm unit is not a service-oriented system. It broadcasts and receives messages; it does not provide services or actions.<br>

**Executes** — Swarm algorithms (aggregation, dispersion, formation, collective transport, synchronisation). The algorithm is selected by the overhead controller or by the firmware configuration.<br>

**Extensions** — Optional sensors (e.g., a temperature sensor, a light sensor, a magnetic sensor) can be added to individual units for distributed sensing experiments. Optional actuators (e.g., a passive gripper, a magnetic attachment) can be added for collective transport experiments.<br>

**Frame conventions** — No global frame. Each unit has its own local frame defined by its orientation. The overhead controller may define a global frame for logging and visualisation, but the swarm units do not use a global frame.<br>

**Units** — SI. Meters, meters/second, radians, seconds.

---

## Model

**URDF / Xacro** — Not typically used for swarm robots. The Kilobot and Zuri do not have URDF models. For simulation, the robot is modelled as a point mass with vibration-driven stochastic motion and IR communication range.<br>

**SDF** — Not typically used. Swarm simulators (ARGoS, Stage) use their own robot models.<br>

**Calibration** — Vibration motor PWM-to-speed calibration (measured for each unit; variation between units is significant). IR communication range calibration (measured for each unit; variation is significant). Phototaxis sensor calibration (measured for each unit; variation is significant). The Kilobot is designed for calibration-free operation; the swarm algorithms are robust to unit-to-unit variation. This is a key design principle: the swarm should not require precise calibration of individual units. The Zuri uses a similar approach.<br>

**Dynamics** — Vibration-driven locomotion is stochastic. The robot's motion is a biased random walk: the mean velocity is determined by the differential motor speeds, and the variance is determined by the vibration amplitude and surface friction. The Kilobot's motion model is a random walk with a bias. The Zuri's magnetic wheel locomotion is more deterministic but still subject to slip and variation. For simulation, the motion model is a stochastic differential equation or a discrete-time random walk. The IR communication model is a distance-dependent probability of reception: closer units have a higher probability of receiving a message. This is the key interaction model for swarm algorithms.<br>

**Sensor transforms** — No external sensors. The IR receiver is on the bottom of the robot (for communication with neighbours). The phototaxis sensor is on the top or side of the robot (for light gradient detection). The vibration motors are on opposite sides of the body. The IR transmitter is on the top of the robot (for broadcasting to neighbours).<br>

**Collision geometry** — Simple circle of radius 16.5 mm (Kilobot: 33 mm diameter).<br>

**Visual geometry** — 3D model of the robot for visualisation. The Kilobot is a simple cylinder with a PCB sandwich. The Zuri is a modular cylinder with magnetic wheels.

---

## Trials

**Bench** — Vibration motor direction and speed. IR transmission and reception. Phototaxis sensor response. Battery voltage and charging. Firmware flashing via IR. Pass/fail, measured values, date. Expected: both vibration motors respond to PWM commands and produce forward motion when driven equally, turning when driven differentially. IR transmitter and receiver communicate at 9600 bps within 10 cm. Phototaxis sensor responds to light gradients. Battery charges to 4.2V and discharges to 3.0V. Firmware flashes successfully via the overhead controller.<br>

**Integration** — Swarm communication test: two units exchange IR messages. Swarm aggregation test: 10 units aggregate into a cluster. Swarm dispersion test: 10 units disperse from a cluster. Swarm formation test: 10 units form a line or a circle. Pass/fail, measured values, date.<br>

**Field** — Aggregation with 100 units. Dispersion with 100 units. Formation with 100 units. Collective transport with 10 units. Synchronisation with 100 units. Pass/fail, measured values, date. The Kilobot has demonstrated all of these behaviours with 100+ units. The Zuri has demonstrated magnetic wheel-based collective behaviours.<br>

**Endurance** — Continuous operation until battery cutoff at 3.0V per cell. Expected runtime: 1–3 hours depending on communication frequency and motor duty cycle.<br>

**Environmental** — Tested on flat indoor surfaces only. Not for carpet, gravel, or outdoor use. IR communication requires controlled indoor lighting.<br>

**Known limitations** — Vibration locomotion is stochastic and imprecise. IR communication is range-limited (10 cm) and directional. No global positioning. No precise localisation. Unit-to-unit variation in vibration motor speed, IR range, and phototaxis sensor response is significant, but the swarm algorithms are designed to be robust to this variation. The swarm requires a controlled arena with a smooth surface and consistent lighting. Scaling to 1000+ units requires careful power management and communication scheduling to avoid IR collisions and battery drain. The swarm has no manipulation capability in the base configuration.

---

## Log

**Build history** — Dated entries, what changed, why.<br>

**Open issues** — Links, priority, status.<br>

**Changelog** — Version bumps, what triggered each.<br>

**Lessons learned** — What would be done differently.<br>

**Cost actual** — Final spend vs. BOM estimate.

---

## Status

**Condition** — draft.<br>

**Blockers** — None. Ready to order parts.<br>

**Next steps** — Finalise BOM, order components, fabricate PCBs, assemble 10 units. Milestone 1: bench test individual units (vibration motors, IR communication, phototaxis). Milestone 2: two-unit communication test. Milestone 3: 10-unit aggregation and dispersion. Milestone 4: 100-unit swarm. Milestone 5: 1000-unit swarm. Milestone 6: collective transport and self-assembly. Milestone 7: optional evolutionary robotics experiments. Milestone 8: optional integration with a host PC for swarm monitoring and control.

---

**Note on this Shell:** The swarm robot is a distinct platform class in the library. Unlike all other platforms, the swarm unit is not designed for individual capability; it is designed for collective capability. Each unit is deliberately simple, cheap, and imprecise. The intelligence is in the swarm, not in the unit. This makes the swarm platform uniquely suited to research into emergence, self-organisation, and distributed algorithms. The Kilobot (Harvard) and Zuri (open-source) are the reference platforms for this class. The Kilobot has been used in hundreds of research papers and has demonstrated aggregation, dispersion, formation, collective transport, and synchronisation with up to 1024 units. The Zuri adds magnetic wheels and a modular design for more precise locomotion. This Shell is the reference for a centimetre-scale swarm robot with IR communication, vibration locomotion, and open-source firmware.
