# coral

**Class:** aquatic (biomimetic)<br>
**Generation:** 1<br>
**Version:** 1.0.0<br>
**Glossary:** 2026-09<br>
**Condition:** operational<br>
**Author:** OpenFish / FISHR research lineage<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Open-source biomimetic soft robotic fish for high-speed, efficient underwater locomotion research. Emulates the thunniform swimming pattern (tuna-like) using a combination of an active and passive tail segment, powered by a single DC motor driving an oscillation mechanism. The fish is a research platform for studying fish swimming mechanics, hydrodynamic efficiency, and bio-inspired propulsion. It exists because traditional rigid AUVs sacrifice maneuverability and efficiency for straight-line speed; fish demonstrate superior propulsion efficiency, acceleration, and maneuverability, and the OpenFish platform is designed to replicate these characteristics in a reproducible, open-source form.

**Environment** — Freshwater and saltwater. Pools, lakes, and shallow coastal waters. Maximum depth rating 10 m (the OpenFish design is not pressure-rated for deep operation; the hull is sealed for shallow-water use). Water temperature 0–35 °C. Not for open ocean, high currents, or deep-sea deployment.

**Mission** — Provide a standardized, open-source biomimetic platform for comparative research. The absence of a suitable open-source design has been a significant limitation in robotic fish research, hindering direct comparisons of results due to differences in swimming forms, mechanics, and highly divergent designs. The OpenFish design offers a fundamental platform that is widely accessible and serves as a shared research infrastructure for studying oscillating propulsion, hydrodynamic efficiency, and biomimetic control.

**Operator** — Single operator via wireless gamepad or ROS 2 teleop. The fish can be programmed with pre-defined swim patterns (speed, tail-beat frequency, amplitude) or controlled in real time. Autonomous operation is supported via onboard sensors and a ROS 2 control stack.

**Reusability** — Fully open-source. The OpenFish design is released under a Creative Commons Attribution 4.0 International License (CC BY 4.0), with hardware cost estimated at $286.52 and source files available through the Open Science Framework (OSF) and GitHub repositories. The FISHR (Fluid Interaction Study: Hydrodynamic Robot) expansion simplifies construction, addresses waterproofing issues, and facilitates the development of an autonomous version.

---

## Spec

**Physical** — Body length approximately 500 mm (OpenFish-class). Body diameter approximately 80 mm at the widest point. Total mass approximately 1.2 kg depending on battery and electronics. The fish hull is 3D-printed (PETG or PLA) with a soft tail section. The FISHR redesign modified the fish hull and internal components to simplify construction and address waterproofing issues.

**Kinematic** — Single-degree-of-freedom tail oscillation. The propulsion system uses a single DC motor driving an oscillation mechanism that actuates both an active tail segment and a passive tail segment. This combination of active and passive segments accurately mimics the thunniform swimming pattern, which is characterized by a high aspect-ratio tail fin and a body that oscillates primarily at the caudal peduncle (the narrow region just before the tail fin). The tail-beat frequency range is approximately 0.9–7.0 TB s⁻¹ (tail-beats per second), and the amplitude range is 10°–30°, spanning from the fast, low-amplitude undulation of tuna to slower, higher-amplitude motions.

**Dynamic** — Maximum speed approximately 1.0–1.5 m/s depending on tail-beat frequency and amplitude. The OpenFish design was optimized for speed and efficiency, and the thunniform swimming pattern is one of the most efficient in nature. Propulsion efficiency is significantly higher than propeller-driven AUVs of comparable size, and the acoustic signature is lower due to the absence of a high-speed propeller. Turning radius is proportional to body length and is achieved by asymmetric tail oscillation (bias in the tail sweep).

**Power** — 3S LiPo (11.1 V nominal, 2200 mAh, 24.4 Wh) or 4S LiPo (14.8 V nominal, 1500 mAh, 22.2 Wh). Runtime 30–60 minutes depending on speed and duty cycle. XT30 or XT60 connector. The single DC motor draws 5–15 A depending on load. 5V 3A buck converter for the control board and sensors. 3.3V for the IMU.

**Thermal** — 0–35 °C water temperature operating. Passive cooling by immersion. The motor is mounted in the hull and is cooled by the surrounding water through the hull wall. No active thermal management.

**Environmental** — IP68 for the sealed hull. Depth-rated to 10 m. Not for deep-sea or high-pressure environments. The soft tail section is waterproofed using the FISHR waterproofing techniques.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $290–$500 depending on electronics and battery selection. The base OpenFish hardware cost is $286.52.

**Structure** — 3D-printed rigid hull (PETG or PLA, 2–3 mm wall thickness) with a flexible tail section. The hull houses the motor, battery, control electronics, and sensors. The tail section is fabricated from silicone (Dragonskin or Elastosil) with embedded stiff fin rays within a compliant membrane, or from a compliant polymer with a rigid leading-edge link. The design follows the OpenFish architecture: a single DC motor drives an oscillation mechanism that actuates an active tail segment, and a passive tail segment follows the active segment's motion through hydrodynamic coupling and structural compliance. The FISHR redesign simplified construction and addressed waterproofing issues in the original OpenFish design.

**Actuation** — 1× brushed DC motor or brushless DC motor driving the tail oscillation mechanism. The motor is mounted in the forward hull and drives a crank-rocker or cam-follower mechanism that converts rotary motion into oscillatory tail motion. The active tail segment is directly driven by the mechanism; the passive tail segment is attached to the active segment and follows its motion with a phase lag determined by its structural compliance and hydrodynamic loading. Servo motors are also used in some robotic fish designs, with approximately 50% of bio-inspired swimming robots using servo-type actuators, and servos are extensively used for developing robotic fish.

**Locomotion** — Biomimetic thunniform swimming. The tail oscillates side-to-side at a controlled frequency and amplitude, generating forward thrust through a combination of added mass and circulatory forces. The body (hull) remains largely rigid, with the oscillation concentrated at the caudal peduncle and tail fin, which is the thunniform pattern. Turning is achieved by biasing the tail's oscillation to one side, creating an asymmetric thrust vector. The fish can also perform rapid acceleration (burst swimming) by increasing tail-beat frequency and amplitude temporarily.

**Manipulation** — None. The fish is a propulsion and locomotion research platform.

**Power system** — 3S LiPo 2200 mAh (or 4S LiPo 1500 mAh). XT30/XT60 connector. 11.1 V (or 14.8 V) direct to the motor driver. 5V 3A buck converter for the control board (Teensy 4.0 or STM32) and sensors. 3.3 V for the IMU. Power distribution via a small PCB or wired harness. All power wiring 18 AWG for motor leads, 22 AWG for logic power.

**Wiring** — Motor power: 18 AWG. Motor signal: 26 AWG. Sensor wiring: 26 AWG shielded (I2C or SPI). All wiring routed through the hull with a watertight cable gland at the tail interface. The FISHR design includes waterproofing techniques for the soft robotic fish, including sealing the motor shaft penetration and the hull joint.

**Custom parts** — 3D-printed hull (PETG or PLA). Silicone tail (Dragonskin or Elastosil, cast in a 3D-printed mold). Embedded fin rays (carbon fiber or nylon rods). Oscillation mechanism (3D-printed PETG or machined aluminum). Watertight cable gland (3D-printed TPU or purchased). Hull end cap (3D-printed PETG with O-ring seal).

**Fasteners** — M3 stainless steel (316 marine grade). M3 for hull assembly and motor mounting. Nylon insert lock nuts for vibration-prone connections. All fasteners stainless steel to resist corrosion.

**Tools required** — 3D printer (PETG/PLA capable), silicone casting tools (mold, vacuum chamber for degassing), soldering iron, wire crimper, multimeter, hex drivers (2 mm, 2.5 mm).

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| Brushed DC motor (or brushless) with gearbox | 1 | Pololu / Maxon | ~$30 | Actuators/DC |
| Motor driver (H-bridge, 10A) | 1 | Pololu / Cytron | ~$15 | Actuators/driver |
| Teensy 4.0 or STM32 control board | 1 | PJRC / ST | ~$25 | Compute/MCU |
| BNO085 9-DOF IMU | 1 | Adafruit | ~$25 | Sensors/IMU |
| MS5837-30BA pressure sensor (depth) | 1 | Blue Robotics | ~$50 | Sensors/Depth |
| 3S LiPo 2200 mAh or 4S LiPo 1500 mAh | 1 | Tattu | ~$25 | Power/battery |
| 5V 3A buck converter | 1 | Pololu | ~$8 | Power/converter |
| XT30 connector pair | 1 | Various | ~$3 | Power/connector |
| Silicone (Dragonskin or Elastosil) | 500 g | Smooth-On / Wacker | ~$50 | Soft material/Tail |
| Carbon fiber or nylon fin rays | 10 | Various | ~$10 | Soft material/FinRays |
| 3D-printed hull (PETG or PLA) | 1 set | Local print | ~$15 | Structure/Hull |
| 3D-printed tail mold | 1 | Local print | ~$10 | Fabrication/Mold |
| Watertight cable gland | 1 | Blue Robotics | ~$10 | Sealing/Gland |
| O-ring seals | 4 | McMaster | ~$2 | Sealing/O-ring |
| M3 stainless fasteners | assorted | McMaster | ~$5 | Fasteners |
| 18 AWG, 22 AWG, 26 AWG wire | assorted | Various | ~$10 | Wiring |
| **Total** | | | **~$290–$400** | |

---

## Systems

**Manifest** — The OpenFish and FISHR designs are ROS-compatible. The FISHR expansion includes detailed insights into hardware implementation and facilitates the development of an autonomous version. The control stack can be implemented on a Teensy 4.0 or STM32 running micro-ROS, with a high-level ROS 2 stack on a companion computer (Raspberry Pi Zero 2W or similar).

**Firmware** — The control board runs the tail oscillation control loop at 100–500 Hz. It reads the IMU (orientation), pressure sensor (depth), and motor encoder (if equipped). It generates the tail oscillation waveform (sinusoidal or custom waveform) at the commanded frequency and amplitude. It receives high-level commands (speed, turning rate) from the companion computer or RC receiver over serial or micro-ROS.

**Middleware** — micro-ROS on the control board, ROS 2 Jazzy on the companion computer (optional). For a minimal build without ROS, the control board can be commanded directly via RC PWM or serial. The WHOI-ROS and Orca4 stacks provide reference architectures for ROS 2-based underwater vehicle software, including sensor drivers, navigation, and simulation.

**Perception** — BNO085 9-DOF IMU for orientation and motion sensing. MS5837-30BA pressure sensor for depth measurement (30 bar, ~300 m capability, though the hull is rated to 10 m). Optional: low-light camera (Blue Robotics Low-Light HD USB Camera or 4K Cam with Sony IMX678 sensor) for visual inspection and navigation. The 4K Cam delivers 4K or 1080p resolution with excellent low-light performance, and the Low-Light HD USB Camera has been tested to 300 m depth, where it can see subtle bioluminescent creatures in darkness.

**Control** — The tail oscillation controller generates a sinusoidal (or custom) position command for the motor: `θ(t) = A · sin(2πft)`, where A is the amplitude (10°–30°) and f is the tail-beat frequency (0.9–7.0 TB s⁻¹). The motor driver tracks the position command using a PID or feedforward controller. Speed control is achieved by adjusting frequency and amplitude. Turning control is achieved by adding a bias to the oscillation: `θ(t) = A · sin(2πft) + B`, where B is the bias (positive for left turn, negative for right turn). The passive tail segment follows the active segment with a phase lag determined by its compliance and hydrodynamic loading; this phase lag is a key parameter for optimizing propulsion efficiency.

**Planning** — No autonomous navigation in the base platform. Optional: waypoint navigation using depth and heading hold. Optional: vision-based target tracking using the onboard camera and a simple controller (e.g., the OpenAUV vision-based tracking control system demonstrates this capability on a multi-thruster AUV).

**Learning** — Designed for research into bio-inspired control and reinforcement learning. The platform supports training locomotion policies in simulation (Gazebo with hydrodynamic plugins, or MuJoCo) and deploying them to hardware. The WHOI-ROS and Nerites frameworks provide ROS 2 simulation environments for underwater robotics, including reinforcement learning-ready bridges.

**Teleoperation** — Wireless gamepad or RC transmitter connected to the control board. A ROS 2 node or simple serial interface maps gamepad inputs to speed and turning commands. Video feed (if camera fitted) streamed to the operator via Wi-Fi (if the fish surfaces) or not available (if fully submerged; acoustic communication would be required for submerged video, which is not part of the base platform).

**Safety** — Watchdog: if no command received within 500 ms, the motor stops and the fish glides to a stop. Depth limit: if the pressure sensor reads >10 m, the motor stops and the fish is commanded to ascend (if a depth controller is implemented). Leak detection: optional humidity sensor inside the hull triggers a warning. The soft tail is inherently safe and cannot cause injury.

**Logging** — rosbag2 with MCAP format (if ROS 2 is used). Otherwise, CSV or binary log of tail frequency, amplitude, depth, heading, and timestamps. Data format compatible with LeRobot for future policy training.

**Networking** — Wi-Fi via the companion computer (if fitted) when the fish is at the surface. Underwater acoustic communication is not part of the base platform but could be added for fully submerged operation.

**Config files** — Tail oscillation parameters (frequency, amplitude, bias), motor PID gains, depth limits, safety limits.

**Launch files** — `bringup.launch.py`, `teleop.launch.py`, `logging.launch.py` (if ROS 2 is used).

**Dependencies** — micro-ROS (optional), ROS 2 Jazzy (optional), `bno08x_driver`, `ms5837` driver, `joy` (if gamepad teleoperation), `rosbag2`, `robot_state_publisher`, `rviz2` (optional). Gazebo with underwater hydrodynamics plugins for simulation (buoyancy, lift-drag, control plugins).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ROS 2 (optional) | Jazzy | ros.org | Middleware/ROS2 |
| Ubuntu (optional) | 24.04 LTS | ubuntu.com | OS/Linux |
| micro-ROS | Jazzy-compatible | microros.org | Middleware/microROS |
| bno08x_driver | Latest | index.ros.org | Perception/drivers |
| ms5837 driver | Latest | Blue Robotics | Perception/drivers |
| joy (optional) | Latest | ROS 2 | Teleoperation/input |
| rosbag2 | Latest | ROS 2 | Logging/rosbag |
| robot_state_publisher | Latest | ROS 2 | Model/URDF |
| rviz2 | Latest | ROS 2 | Visualization |
| Gazebo | Harmonic | gazebosim.org | Simulation |

---

## Interface

**Emits** — `/joint_states` (100 Hz, JointState for tail position), `/imu/data` (100 Hz, Imu), `/depth` (10 Hz, Float32 from MS5837), `/robot_status` (1 Hz), `/tf`. Optional `/camera/image_raw` (30 Hz, Image).

**Accepts** — `/cmd_vel` (20 Hz, Twist for forward speed and turning rate), `/tail_params` (20 Hz, custom message for frequency, amplitude, bias), `/teleop_input` (20 Hz from gamepad).

**Serves** — `/enable`, `/disable`, `/calibrate`, `/home` (tail to center position).

**Executes** — `/swim` (action, swim for distance or time), `/turn` (action, turn to heading), `/dive` (action, descend to depth), `/surface` (action, ascend to surface).

**Extensions** — `coral/tail_phase`, `coral/tail_amplitude`, `coral/motor_current`, `coral/battery_state`, `coral/leak_status`.

**Frame conventions** — `base_link` at the fish center of mass. `base_footprint` at the fish center projected downward. `tail_link` at the tail base. `tail_tip` at the tail fin. `imu_link` at the IMU position. `depth_link` at the pressure sensor. `camera_link` at the camera position (if fitted).

**Units** — SI. Meters, meters/second, radians, seconds, Hertz (tail-beat frequency), degrees (amplitude), bar (pressure).

---

## Model

**URDF / Xacro** — `model/coral.urdf.xacro`. Includes 1 revolute joint for the tail, plus fixed links for the hull, IMU, depth sensor, and camera. Joint limits: tail angle ±30°. Links: hull, tail_active, tail_passive, tail_fin.

**SDF** — Used for Gazebo simulation with underwater hydrodynamics plugins. The simulation includes buoyancy, lift-drag, and control plugins to model the fish's motion in water.

**Calibration** — Motor zero offset (tail center position). IMU orientation and bias. Pressure sensor offset (surface pressure = 0 m). Tail oscillation amplitude calibration (measured tail angle vs. commanded angle). Tail-beat frequency calibration (measured oscillation frequency vs. commanded frequency).

**Dynamics** — Motor constants from datasheet. Tail mechanism inertia and friction identified through system identification. The passive tail segment's compliance and hydrodynamic coupling are characterized through tank testing (measuring tail phase lag vs. frequency). Hydrodynamic coefficients (added mass, drag) identified through CFD simulations and tank experiments, following the approach used for the OpenAUV platform.

**Sensor transforms** — IMU at hull center. Pressure sensor at hull bottom. Camera at hull front (if fitted). Tail joint at the caudal peduncle.

**Collision geometry** — Simplified cylinder for the hull and a flat plate for the tail in simulation.

**Visual geometry** — STL meshes from the 3D-printed hull and silicone tail.

---

## Trials

**Bench** — Motor direction, tail oscillation amplitude and frequency, IMU readings, pressure sensor reading. Pass/fail, measured values, date. Expected: motor oscillates the tail at the commanded frequency (0.9–7.0 Hz) and amplitude (10°–30°), IMU reports orientation within 2° accuracy, pressure sensor reads 0 m at surface.

**Integration** — Control board bring-up, micro-ROS link (if used), teleoperation latency, tail phase lag measurement (passive tail follows active tail with a phase lag that varies with frequency). Pass/fail, measured values, date.

**Field** — Pool test: swim at 0.5 m/s, 1.0 m/s, and 1.5 m/s; measure actual speed vs. commanded speed; measure turning radius. Lake test (calm conditions): depth control to 5 m; waypoint navigation (if fitted). Endurance test: continuous swim until battery cutoff. Pass/fail, measured values, date.

**Endurance** — Continuous swim until battery cutoff at 3.3 V per cell. Motor temperature at end (water-cooled, expected <40 °C).

**Environmental** — Tested in freshwater pool and calm lake. Depth-rated to 10 m. Not for high currents or open ocean.

**Known limitations** — The soft tail is subject to wear and fatigue over repeated oscillation cycles. The passive tail segment's performance depends on the silicone material properties, which vary with temperature and age. The single-DOF tail limits maneuverability compared to multi-fin designs (e.g., pectoral fins for hovering). The acoustic signature is lower than a propeller-driven AUV, but not silent. The OpenFish design is optimized for speed and efficiency, not for hovering or precise station-keeping. The absence of a commercial analog means all components must be sourced and assembled individually.

---

## Log

**Build history** — Dated entries, what changed, why. The design is based on the OpenFish (Delft University of Technology) and the FISHR expansion (2025). The FISHR redesign simplified construction, addressed waterproofing issues, and facilitated the development of an autonomous version.

**Open issues** — Links, priority, status. Tail fatigue life. Silicone material aging. Autonomous navigation without GPS (underwater localization). Acoustic communication for fully submerged operation. Scaling to larger sizes.

**Changelog** — Version bumps, what triggered each.

**Lessons learned** — The combination of an active and passive tail segment accurately mimics the thunniform swimming pattern and achieves high propulsion efficiency. The absence of an open-source design was a significant limitation in robotic fish research; the OpenFish platform addresses this by providing a reproducible, standardized platform for comparative studies. The FISHR redesign demonstrated that construction can be simplified and waterproofing improved without sacrificing performance.

**Cost actual** — Base OpenFish hardware cost: $286.52. FISHR cost not specified separately. Full build with battery, control board, and sensors: approximately $290–$500.

---

## Status

**Condition** — operational.

**Blockers** — None. Open-source design available.

**Next steps** — Finalise BOM, source components, 3D print hull and tail mold, cast silicone tail, assemble. Milestone 1: bench test tail oscillation and sensors. Milestone 2: pool test at low speed. Milestone 3: speed sweep (0.5–1.5 m/s) and turning radius measurement. Milestone 4: depth control and endurance test. Milestone 5: optional ROS 2 integration and logging. Milestone 6: optional camera and vision-based navigation. Milestone 7: optional autonomous waypoint navigation.

---

**Note on this Shell:** The coral (biomimetic fish) is a distinct class in the library. Unlike propeller-driven AUVs, it derives propulsion from oscillating appendages, mimicking the thunniform swimming pattern of tuna. The engineering principles — active + passive tail segments, hydrodynamic coupling, and soft material compliance — are fundamentally different from rigid-body robotics. The OpenFish platform is the reference for open-source biomimetic fish design, providing a reproducible, standardized platform for comparative research at a hardware cost of $286.52. The FISHR expansion simplifies construction and enables autonomous operation. This Shell is the reference for a bio-inspired underwater robot with a soft tail, single-DOF oscillation, and open-source design files.
