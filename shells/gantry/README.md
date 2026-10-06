# gantry

**Class:** stationary (gantry)<br>
**Generation:** 1<br>
**Version:** 1.0.0<br>
**Glossary:** 2026-09<br>
**Condition:** operational<br>
**Author:** GTEC-UDC / University of A Coruña<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Large high-precision 3-axis Cartesian gantry robot system for positioning sensors, tools, or end effectors across a fixed planar workspace. The gantry spans a working volume of 5.3 m × 5.2 m × 1 m and achieves sub-centimeter precision across the entire envelope using closed-loop control and a custom calibration solution. Unlike arm-based manipulators, the gantry's load is carried by the frame, not by the actuators, so the moving mass is small and the structural stiffness is high. This makes it the best platform class for large, flat work areas where precision and stability matter more than reach or dexterity.<br>

**Environment** — Indoor, fixed installation. Laboratory, factory floor, or research facility. The frame is anchored to the floor or ceiling. Not for outdoor use, mobile deployment, or environments with significant vibration.<br>

**Mission** — Position and move a payload (sensor, probe, tool, camera) across a large planar workspace with high precision and repeatability. The gantry is a positioning platform, not a manipulator; it moves a point in X, Y, and Z. Applications include automated material handling, large-scale 3D printing, automated inspection, pick-and-place across large work areas, and laboratory automation.<br>

**Operator** — Single operator via LinuxCNC GUI (Axis or GMOCCAPY) on a dedicated control PC. G-code programming or jogging. Optional integration with higher-level software for automated task execution.<br>

**Reusability** — Fully open-source design. All design files, electrical schematics, and calibration software are available in the repository. Structural components are standard off-the-shelf parts from igus and Mesa Electronics. Repeatable build.

---

## Spec

**Physical** — Working volume 5.3 m (X) × 5.2 m (Y) × 1 m (Z). Total footprint approximately 6.5 m × 6.5 m × 1.5 m including frame and overtravel. Frame constructed from igus drylin linear guide rails and self-lubricating linear units. Moving mass consists of the Z-axis carriage and end effector only; the heavy motors are mounted on the frame. The gantry is designed to be anchored to the floor for stability.<br>

**Kinematic** — 3 linear axes: X (bridge travel), Y (carriage travel along bridge), Z (vertical travel). Cartesian kinematic structure. The bridge spans the Y-axis and moves along the X-axis rails. The carriage moves along the bridge (Y-axis). The Z-axis is mounted on the carriage and moves vertically. This is a classic gantry configuration: two motors drive the X-axis (one on each side of the bridge), one motor drives the Y-axis, and one motor drives the Z-axis. A LinuxCNC `gantry` HAL component drives multiple physical motors from a single axis input for the dual-motor X-axis, ensuring the bridge stays square. Up to seven joints can be controlled from a single axis input if needed. <br>

**Dynamic** — Payload capacity not specified in the source, but the gantry is designed for sensor and tool positioning rather than heavy lifting. Positioning precision sub-centimeter (≤10 mm) across the entire work envelope, achieved through closed-loop encoder feedback and OptiTrack-based calibration. Speed and acceleration not specified; the igus linear units are designed for continuous operation with self-lubrication. <br>

**Power** — 3 NEMA 34 brushless motors (X and Y axes) and 1 NEMA 24 stepper motor (Z axis). Motor controllers: igus dryve D1. Power requirements not specified but typical for NEMA 34 motors: 48–70 V DC, 5–10 A per motor. <br>

**Thermal** — Passive cooling. Motors and controllers are mounted on the frame with air circulation. No active thermal management specified. <br>

**Environmental** — Indoor, fixed installation. Temperature and humidity not specified. Not for outdoor or hazardous environments. <br>

---

## Frame

**Bill of materials** — The full BOM is derived from the repository documentation, including KiCAD electrical schematics and mechanical drawings. Total estimated cost ≈ $15,000–$25,000 depending on sourcing and configuration.<br>

**Structure** — The frame uses igus drylin linear guide rails and self-lubricating linear units. These are self-lubricating, enabling lifelong operation of the moving parts without external lubrication. The X-axis rails are mounted on the floor or a raised foundation on both sides of the workspace. The Y-axis bridge spans between the two X-axis rails. The Z-axis is mounted on the carriage that travels along the bridge. The structure is designed for rigidity and stability across the 5.3 m × 5.2 m work envelope. <br>

**Actuation** — 3× NEMA 34 brushless motors for X and Y axes. 1× NEMA 24 stepper motor for Z axis. Motor controllers are igus dryve D1, which are integrated with LinuxCNC via Mesa Electronics interface cards. The dryve D1 controllers provide closed-loop control with encoder feedback. The dual X-axis motors are driven from a single LinuxCNC axis through the `gantry` HAL component, which ensures the bridge remains square during motion. The `gantry` component supports up to seven joints from a single axis input. <br>

**Locomotion** — Fixed base. Linear motion along X, Y, and Z axes. The gantry does not locomote. The workspace is fixed and the entire work envelope is accessible from the gantry's frame.<br>

**Manipulation** — None. The gantry is a positioning platform. A tool or sensor is mounted on the Z-axis carriage via a standard mounting interface. The payload is whatever the user mounts: camera, probe, gripper, 3D print head, etc.<br>

**Power system** — Power distribution not fully specified. The dryve D1 controllers accept 24–48 V DC input. A central power supply (likely 48 V, 20–30 A) powers the four motor controllers and the control electronics. All power wiring should be appropriately sized for the current draw (10–12 AWG for main bus, 16 AWG for per-controller power).<br>

**Wiring** — Motor power and encoder cables run along the frame with cable carriers (drag chains) to manage motion. The X-axis cable carrier runs the length of the X-axis rails. The Y-axis cable carrier runs along the bridge. The Z-axis cable carrier runs vertically. Mesa Electronics interface cards connect the LinuxCNC control PC to the dryve D1 controllers via Ethernet or parallel port. <br>

**Custom parts** — The repository includes custom mechanical designs for motor mounts, carriage assemblies, and end effector mounting plates. Electrical schematics are provided in KiCAD format. A custom `calibxyzkins` LinuxCNC kinematics module is provided for real-time compensation of positioning errors.<br>

**Fasteners** — Standard metric fasteners. The igus linear units use their own mounting hardware. All fasteners should be appropriately sized for the static and dynamic loads of the gantry structure.<br>

**Tools required** — LinuxCNC control PC (Ubuntu with real-time kernel, or Debian). Mesa Electronics interface cards (e.g., 7i76, 7i77). igus dryve D1 motor controllers. OptiTrack motion capture system (for calibration). Standard metric hex drivers, torque wrench, multimeter.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| NEMA 34 brushless motor (X and Y axes) | 3 | Various | ~$200 each | Actuators/BLDC |
| NEMA 24 stepper motor (Z axis) | 1 | Various | ~$100 | Actuators/Stepper |
| igus dryve D1 motor controller | 4 | igus | ~$400 each | Actuators/driver |
| igus drylin linear guide rails and units | 1 set | igus | ~$8,000 | Structure/Linear |
| Mesa Electronics 7i76 interface card | 1 | Mesa | ~$200 | Control/Interface |
| Mesa Electronics 7i77 interface card | 1 | Mesa | ~$200 | Control/Interface |
| LinuxCNC control PC | 1 | Various | ~$800 | Compute/PC |
| Control cabinet and power supply | 1 | Various | ~$1,500 | Power/Enclosure |
| Cable carriers (drag chains) | 3 | igus | ~$300 each | Wiring/CableCarrier |
| Encoders (closed-loop feedback) | 4 | Various | ~$150 each | Sensors/Encoder |
| OptiTrack motion capture system | 1 | OptiTrack | ~$5,000–$15,000 | Calibration/OptiTrack |
| Emergency stop and safety hardware | 1 set | Various | ~$500 | Safety |
| Fasteners and mounting hardware | assorted | McMaster | ~$500 | Fasteners |
| Cable and wiring | assorted | Various | ~$500 | Wiring |

---

## Systems

**Manifest** — The software stack is LinuxCNC-based. LinuxCNC is an open-source motion control system that provides G-code interpretation, trajectory planning, and real-time motor control. The repository includes custom HAL components and a kinematics module for calibration compensation. <br>

**Firmware** — The igus dryve D1 controllers run their own motor control firmware. The Mesa Electronics interface cards provide the hardware interface between the LinuxCNC PC and the motor controllers. The LinuxCNC PC runs a real-time kernel (RTAI or PREEMPT_RT) for deterministic motion control. <br>

**Middleware** — LinuxCNC HAL (Hardware Abstraction Layer). HAL is a software bus that connects motion control modules, I/O modules, and user interface modules. The `gantry` HAL component drives multiple joints from a single axis input. The custom `calibxyzkins` kinematics module compensates for positioning errors in real time using calibration parameters generated from OptiTrack measurements. <br>

**Perception** — Encoders on each axis provide closed-loop position feedback. No external perception sensors are included in the base gantry. Optional: cameras, probes, or other sensors mounted on the Z-axis carriage for specific applications. <br>

**Control** — LinuxCNC provides the motion control loop. The control loop runs in the LinuxCNC real-time thread at 1 kHz or higher. The `gantry` HAL component coordinates the dual X-axis motors. The custom `calibxyzkins` kinematics module applies real-time compensation for positioning errors. Closed-loop control with encoder feedback ensures accurate positioning. The system was developed from the LinuxCNC motor control testbed, which ensured the main components of the system were able to work reliably. <br>

**Planning** — G-code trajectory planning via LinuxCNC. Trajectory blending, look-ahead, and feed rate override. Optional integration with higher-level software (Python, ROS) for task planning and automated execution. <br>

**Learning** — None. The gantry is a positioning platform; learning is not applicable to its primary function. <br>

**Teleoperation** — LinuxCNC GUI (Axis or GMOCCAPY) for jogging and manual control. MPG (manual pulse generator) handwheel for precise manual positioning. Optional gamepad integration for remote jogging. <br>

**Safety** — LinuxCNC supports hardware emergency stop, limit switches, and soft limits. The system includes an emergency stop button and safety interlocks. The dual-motor X-axis is coordinated by the `gantry` component to prevent racking (the bridge twisting out of square), which could damage the linear guides or cause a collision. <br>

**Logging** — LinuxCNC logs axis positions, following errors, and machine state. Custom logging can be added via HAL. Position data can be logged for post-motion analysis and calibration verification. <br>

**Networking** — Ethernet connection between the LinuxCNC PC and the Mesa interface cards. Ethernet between the LinuxCNC PC and the igus dryve D1 controllers. Optional remote access via SSH or VNC for monitoring and control. <br>

**Config files** — LinuxCNC INI and HAL files configure the machine kinematics, motor scaling, limits, and GUI. The `gantry` component is loaded in the HAL file. The `calibxyzkins` kinematics module is configured with calibration parameters generated from OptiTrack measurements. <br>

**Launch files** — LinuxCNC is launched from the command line or a desktop shortcut. No ROS-style launch files are used. <br>

**Dependencies** — LinuxCNC (with real-time kernel). Mesa Electronics drivers. igus dryve D1 configuration software. Python for calibration analysis. OptiTrack Motive software for calibration measurements.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| LinuxCNC | 2.9+ | linuxcnc.org | Control/CNC |
| Mesa Electronics drivers | Latest | mesa | Control/drivers |
| igus dryve D1 configuration | Latest | igus | Actuators/driver |
| Python | 3.x | python.org | Calibration/Analysis |
| NumPy | Latest | numpy.org | Calibration/Math |
| SciPy | Latest | scipy.org | Calibration/Math |
| OptiTrack Motive | Latest | optitrack.com | Calibration/MoCap |

---

## Interface

**Emits** — Axis positions, following errors, machine state, limit switch status, encoder feedback. G-code status. <br>

**Accepts** — G-code programs. Jog commands via GUI or MPG. MDI (Manual Data Input) commands. HAL pin signals for external control. <br>

**Serves** — LinuxCNC HAL pins for integration with external software. Axis enable/disable, homing, and fault handling. <br>

**Executes** — G-code programs for 3-axis motion. Trajectory following with look-ahead. Coordinated multi-axis moves. <br>

**Extensions** — Custom HAL components. Python scripts for automation. ROS 2 integration via `ros2_control` (optional, not in the base build). <br>

**Frame conventions** — X, Y, Z Cartesian coordinates. Machine coordinate system and work coordinate systems (G54–G59). <br>

**Units** — Millimeters or inches (configurable in LinuxCNC INI file). Millimeters per minute or inches per minute for feed rates.

---

## Model

**URDF / Xacro** — Not typically used for gantry robots. LinuxCNC uses its own kinematic model defined in the INI and HAL files. <br>

**SDF** — Not typically used. <br>

**Calibration** — The gantry is calibrated using an OptiTrack motion capture system. The calibration software analyzes OptiTrack measurements and generates calibration parameters that are loaded into the custom `calibxyzkins` LinuxCNC kinematics module. The calibration compensates for positioning errors in real time across the entire work envelope, achieving sub-centimeter precision. The repository includes Python scripts for processing OptiTrack data and generating calibration parameters. <br>

**Dynamics** — The gantry dynamics are relatively simple compared to arm-based manipulators. The moving mass is the bridge (Y-axis), carriage, Z-axis, and payload. Inertia varies with payload and Z-axis extension. LinuxCNC handles the motion control with PID loops for each axis. The dual X-axis motors are coordinated to keep the bridge square. <br>

**Sensor transforms** — Encoders are mounted on each axis. No external perception sensors in the base configuration. <br>

**Collision geometry** — Soft limits in LinuxCNC prevent the gantry from colliding with the frame or exceeding the work envelope. <br>

**Visual geometry** — Not applicable.

---

## Trials

**Bench** — Motor direction, encoder counts, limit switches, e-stop, homing sequence. Pass/fail, measured values, date. <br>

**Integration** — LinuxCNC bring-up. Mesa interface card communication. igus dryve D1 controller communication. HAL component loading. `gantry` component operation (dual X-axis coordination). `calibxyzkins` kinematics module operation. Pass/fail, measured values, date. <br>

**Field** — Precision calibration using OptiTrack. Positioning accuracy measurement across the work envelope. Repeatability test. Load test with representative payload. Speed and acceleration test. Pass/fail, measured values, date. <br>

**Endurance** — Continuous operation over the full work envelope. Motor temperature monitoring. Linear guide wear inspection. <br>

**Environmental** — Indoor, fixed installation. Temperature and humidity not specified. Not for outdoor or hazardous environments. <br>

**Known limitations** — Fixed workspace; the gantry cannot move to another location. Large footprint; requires significant floor space. Calibration requires an OptiTrack motion capture system, which is expensive and not part of the base gantry cost. Sub-centimeter precision is impressive for a 5.3 m × 5.2 m gantry, but not comparable to a small delta or arm robot for fine manipulation. The gantry is a positioning platform; it does not provide orientation (rotation) without an additional rotary axis. The dual-motor X-axis requires careful coordination; if the `gantry` component fails or is misconfigured, the bridge can rack and damage the linear guides.

---

## Log

**Build history** — Developed from the LinuxCNC motor control testbed. The repository includes Sphinx documentation for the system. The gantry was developed by GTEC-UDC at the University of A Coruña. <br>

**Open issues** — Not specified. <br>

**Changelog** — Not specified. <br>

**Lessons learned** — The testbed approach ensured reliability of the main components before full system integration. The custom calibration solution using OptiTrack was necessary to achieve sub-centimeter precision across the large work envelope. <br>

**Cost actual** — Not specified. Estimated $15,000–$25,000 depending on OptiTrack system and sourcing.

---

## Status

**Condition** — operational.<br>

**Blockers** — None. Open-source design available. OptiTrack system required for full calibration.<br>

**Next steps** — Source igus linear units and dryve D1 controllers. Assemble frame and X-axis rails. Mount bridge and Y-axis. Mount Z-axis and carriage. Wire motors and encoders. Install Mesa interface cards. Configure LinuxCNC with `gantry` and `calibxyzkins`. Calibrate with OptiTrack. Run precision and repeatability tests.

---

**Note on this Shell:** The gantry robot is a stationary platform class. Unlike mobile platforms, it trades reach and dexterity for precision, stability, and a large work envelope. It is the best platform class for applications where the workspace is fixed and the task requires positioning a sensor or tool across a large area. The open-source design from GTEC-UDC provides a complete reference for building a large, high-precision gantry robot.
