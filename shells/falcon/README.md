# falcon

**Class:** parallel<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Three-degree-of-freedom delta robot for high-speed pick-and-place, sorting, and assembly tasks. Uses a parallel kinematic structure with three articulated arms driving a small moving platform. The parallel architecture provides high stiffness, low moving mass, and accelerations up to 10g, making it the fastest manipulator class for repetitive pick-and-place operations in food packaging, electronics assembly, and pharmaceutical sorting.<br>

**Environment** — Indoor, structured, controlled environment. Food-grade, pharmaceutical, or electronics assembly settings. IP54 or IP65 depending on sealing. Operating temperature 5–40 °C. Not for outdoor, hazardous, or explosive atmospheres.<br>

**Mission** — High-speed pick-and-place within a defined workspace. The delta robot picks objects from a conveyor and places them into packages, trays, or sorting bins. Cycle times as low as 0.4 seconds for a full pick-and-place motion. Repeatability ±0.1 mm. The platform is fixed-base; the workspace is directly below the robot.<br>

**Operator** — Single operator via teach pendant or PC-based programming interface. The robot is programmed with waypoints or taught by hand-guiding (if backdrivable). Production runs are fully autonomous after programming.<br>

**Reusability** — Repeatable build from off-the-shelf and 3D-printed components. Open-source designs exist (e.g., OpenDelta, Delta Robot projects on GitHub). Production candidate for research and light industrial tasks.

---

## Spec

**Physical** — Target 12 kg total mass (base + arms + platform). Base frame 400 × 400 mm. Workspace diameter 600 mm. Workspace height 200 mm. Maximum reach 400 mm from base center. Carbon fiber arm links (12 mm outer diameter tubes) with aluminum base and 3D-printed PA12-CF joint housings. Moving platform (end effector mount) 80 mm diameter, 120 g mass.<br>

**Kinematic** — 3 degrees of freedom: X, Y, Z translation. No rotation (3-DOF delta). Three identical arms spaced 120° apart around the base. Each arm has a proximal link (upper arm) driven by a rotary actuator at the base, and a distal link (forearm) connecting to the moving platform via ball joints. Parallel kinematic structure. Inverse kinematics: given a target (x, y, z) position, solve for the three motor angles. Forward kinematics: given three motor angles, solve for the platform position. The workspace is a complex shape defined by the intersection of three spherical shells. Maximum workspace diameter 600 mm at mid-height, tapering at top and bottom.<br>

**Dynamic** — Payload capacity 1 kg (including end effector). Maximum acceleration 10g (98 m/s²) with 0.5 kg payload. Maximum velocity 10 m/s at the platform. Cycle time 0.4–0.6 s for a 300 mm vertical pick-and-place motion with 0.5 kg payload. Repeatability ±0.1 mm. The low moving mass (arms and platform only) enables high acceleration; the heavy actuators are fixed to the base.<br>

**Power** — 48V DC input from external power supply. 3× brushless servo drives, each drawing up to 15A peak. Total peak power 2,200 W. Average power 400–800 W depending on duty cycle. 24V 5A buck converter for control electronics. 5V 3A for sensors and compute. XT90 connector for main power input.<br>

**Thermal** — 5–40 °C operating. Passive cooling. Motors have aluminum heat sinks. Drives have integrated heat sinks. No active cooling required for duty cycles below 50%. For continuous high-speed operation, forced air cooling may be required.<br>

**Environmental** — Indoor, controlled. Not for outdoor use. Not for explosive atmospheres. IP54 or IP65 with additional sealing. Food-grade versions require washdown-rated components and stainless steel hardware.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $3,500–$5,000.<br>

**Structure** — Aluminum 6061-T6 base frame (400 × 400 × 20 mm, CNC-milled or waterjet-cut). Three actuator mounting brackets (6061-T6, CNC-milled or 3D-printed PA12-CF). Carbon fiber upper arms (12 mm OD × 10 mm ID tubes, 250 mm length, 3K weave). Carbon fiber forearms (10 mm OD × 8 mm ID tubes, 400 mm length, 3K weave). 3D-printed PA12-CF joint housings for the elbow and wrist joints. Aluminum ball joint sockets. The moving platform is 3D-printed PA12-CF with mounting holes for end effectors. The delta structure is inherently stiff because loads are carried in tension and compression through the parallel links, not in bending.<br>

**Actuation** — 3× brushless servo motors with harmonic or cycloidal reducers. Selected motor: T-Motor AK80-9 or equivalent. The AK80-9 is a quasi-direct drive (QDD) actuator with a 9:1 planetary reducer, 24 N·m peak torque, 48V input, integrated FOC driver, and CAN bus communication. It provides high torque density, backdrivability, and precise torque control. Alternatively, for lower-cost builds, 3× NEMA 34 stepper motors with 10:1 planetary reducers and closed-loop drivers can be used, but they are heavier and less responsive. The harmonic drive option provides zero backlash and high torque density but at higher cost.<br>

**Locomotion** — Fixed base. The robot does not locomote. The workspace is fixed relative to the base. If mobility is required, the delta robot can be mounted on a linear rail or a mobile platform.<br>

**Manipulation** — Three degrees of freedom (X, Y, Z translation). End effector mounting on the moving platform. Common end effectors: vacuum gripper (for flat objects), pneumatic gripper (for boxes), magnetic gripper (for ferrous objects), or a custom tool. The delta robot does not provide rotation; if rotation is required, a fourth rotary axis can be added to the platform (4-DOF delta).<br>

**Power system** — 48V DC external power supply (e.g., 48V 20A switching power supply). XT90 connector. 24V 5A buck for control electronics. 5V 3A buck for sensors and compute. Power distribution board with XT90 input and XT60 outputs for the three servo drives. All power wiring 12 AWG for main leads, 14 AWG for per-drive power, 22 AWG for signal.<br>

**Wiring** — Servo drive power: 14 AWG. Servo drive communication: CAN bus daisy-chain, 26 AWG shielded. Encoder wiring: integrated in servo drive cable. Sensor wiring: 26 AWG. All wiring routed through the base frame with cable management clips. Service loops at arm joints.<br>

**Custom parts** — 3D-printed PA12-CF joint housings (6: 3 elbow, 3 wrist). 3D-printed PA12-CF moving platform. 3D-printed PA12-CF actuator mounting brackets. Aluminum base frame (waterjet or CNC). Carbon fiber tubes (cut to length). Aluminum ball joint sockets.<br>

**Fasteners** — M4 and M5 stainless steel. M4 for joint housings and platform. M5 for actuator mounting and structural connections. M3 for electronics mounting. Nylon insert lock nuts for vibration-prone connections. Thread locker (blue) on all structural fasteners.<br>

**Tools required** — 3D printer (PA12-CF capable), hex drivers (2 mm, 2.5 mm, 3 mm, 4 mm), soldering iron, wire crimper, multimeter, torque wrench, carbon fiber cutting tool (diamond blade or abrasive wheel), ball joint press.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| T-Motor AK80-9 QDD actuator (48V, 9:1, CAN) | 3 | T-Motor | ~$350 each | Actuators/BLDC |
| CAN transceiver for host (if not onboard) | 1 | Various | ~$5 | Comms/CAN |
| 120 ohm termination resistors | 2 | Various | ~$1 | Comms/CAN |
| Teensy 4.0 | 1 | PJRC | ~$25 | Compute/MCU |
| Raspberry Pi 5, 8 GB | 1 | Raspberry Pi | ~$80 | Compute/SBC |
| Raspberry Pi 5 active cooler | 1 | Raspberry Pi | ~$5 | Compute/cooling |
| 128 GB NVMe SSD + M.2 HAT | 1 | Various | ~$40 | Compute/storage |
| BNO085 9-DOF IMU (optional, for base vibration monitoring) | 1 | Adafruit | ~$25 | Sensors/IMU |
| 48V 20A switching power supply | 1 | Mean Well / Delta | ~$150 | Power/supply |
| 24V 5A buck converter | 1 | Pololu | ~$20 | Power/converter |
| 5V 3A buck converter | 1 | Pololu | ~$8 | Power/converter |
| XT90 connector pair | 1 | Various | ~$5 | Power/connector |
| XT60 connector pairs | 3 | Various | ~$5 each | Power/connector |
| Power distribution board | 1 | Various | ~$30 | Power/distribution |
| Carbon fiber tube, 12 mm OD × 10 mm ID, 1 m | 1 | CST The Composites Store | ~$25 | Structure |
| Carbon fiber tube, 10 mm OD × 8 mm ID, 1 m | 1 | CST | ~$20 | Structure |
| Aluminum 6061-T6 base plate, 400×400×20 mm | 1 | SendCutSend | ~$80 | Structure |
| Aluminum ball joint sockets | 6 | Various | ~$15 each | Structure/Joints |
| Ball joints (rod ends, M5) | 6 | McMaster | ~$8 each | Structure/Joints |
| 12 AWG, 14 AWG, 22 AWG, 26 AWG silicone wire | assorted | Various | ~$25 | Wiring |
| M3, M4, M5 stainless screws, lock nuts | assorted | McMaster | ~$30 | Fasteners |
| PA12-CF filament | ~500 g | Bambu / Shapeways | ~$50 | Custom parts |
| Cable management clips | assorted | Various | ~$10 | Wiring |
| PC or laptop for programming | 1 | Various | ~$800 | Operator interface |
| Teach pendant or gamepad (optional) | 1 | Various | ~$50 | Operator interface |

---

## Systems

**Manifest** — See detailed manifest below.<br>

**Firmware** — Teensy 4.0 runs the real-time inverse kinematics and trajectory generation at 1 kHz. It receives target positions from the Raspberry Pi 5 over micro-ROS serial. It computes the three motor angles using the closed-form inverse kinematics solution for the delta robot. It sends position or torque commands to the three AK80-9 servo drives over CAN bus. Each AK80-9 runs its own FOC and position control loop internally at 20–40 kHz. The Teensy reads the BNO085 IMU (optional) for vibration monitoring. Raspberry Pi 5 runs Ubuntu 24.04 LTS and ROS 2 Jazzy.<br>

**Middleware** — ROS 2 Jazzy. micro-ROS between Teensy 4.0 and Raspberry Pi 5 over USB serial at 921600 baud. Cyclone DDS on the LAN for remote visualization and programming. MoveIt 2 for motion planning (optional; the delta robot can also be programmed with direct waypoints).<br>

**Perception** — Optional. The delta robot does not require onboard perception for basic pick-and-place. Optional: a downward-facing camera on the moving platform for object detection and pose estimation. Optional: a conveyor-mounted camera for object tracking. The BNO085 IMU is optional and used for monitoring base vibration and detecting collisions.<br>

**Control** — Teensy runs inverse kinematics at 1 kHz. The inverse kinematics solution for a delta robot with three arms is a closed-form trigonometric solution. Given a target position (x, y, z), the three motor angles (θ1, θ2, θ3) are computed directly. The trajectory generator produces smooth motion profiles (S-curve or trapezoidal) between waypoints, with acceleration and jerk limits. The AK80-9 drives receive position commands and run their own position control loop. For force-controlled tasks (e.g., press-fitting), torque commands can be sent instead.<br>

**Planning** — MoveIt 2 for motion planning if using the ROS 2 stack. For simple pick-and-place, the robot is programmed with waypoints and the trajectory generator interpolates between them. Pick-and-place sequences are defined as state machines: move to pick position, close gripper, move to place position, open gripper, return to home.<br>

**Learning** — None initially. The delta robot is primarily used for high-speed repetitive tasks. Optional: learning-based grasp point selection using a camera and a trained model. Optional: reinforcement learning for optimizing pick-and-place trajectories.<br>

**Teleoperation** — Not typically teleoperated. The delta robot is programmed and runs autonomously. Optional: gamepad or teach pendant for jogging the robot during setup. Optional: VR teleoperation for remote pick-and-place (uncommon due to the fixed workspace).<br>

**Safety** — Software e-stop. Joint torque limits enforced in the AK80-9 drives. Watchdog: if no command received within 200 ms, motors hold position. Workspace limits enforced in the trajectory generator. Collision detection via motor current monitoring: if current exceeds a threshold (indicating unexpected contact), the robot stops and retracts. Physical e-stop button on the base frame. Light curtain or safety fence around the workspace for industrial deployments.<br>

**Logging** — rosbag2 with MCAP format. Joint positions, velocities, torques, and commanded positions recorded at 1 kHz. Optional camera at 30 Hz. Data format compatible with LeRobot for future policy training.<br>

**Networking** — Ethernet via Raspberry Pi 5 onboard. Wi-Fi optional. SSH over Tailscale for secure remote access.<br>

**Config files** — URDF (`falcon.urdf.xacro`), inverse kinematics parameters (`ik_params.yaml`), trajectory limits (`trajectory_params.yaml`), CAN bus config, gamepad mapping.<br>

**Launch files** — `bringup.launch.py`, `teleop.launch.py`, `pick_place.launch.py`, `logging.launch.py`.<br>

**Dependencies** — ROS 2 Jazzy, `micro_ros_arduino`, `bno08x_driver` (optional), `joy` (optional), `robot_state_publisher`, `rviz2`, `rosbag2`, `MoveIt 2` (optional).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ROS 2 | Jazzy | ros.org | Middleware/ROS2 |
| Ubuntu | 24.04 LTS | ubuntu.com | OS/Linux |
| micro-ROS | Jazzy-compatible | microros.org | Middleware/microROS |
| bno08x_driver (optional) | Latest | index.ros.org | Perception/drivers |
| joy (optional) | Latest | ROS 2 | Teleoperation/input |
| rosbag2 | Latest | ROS 2 | Logging/rosbag |
| robot_state_publisher | Latest | ROS 2 | Model/URDF |
| rviz2 | Latest | ROS 2 | Visualization |
| Foxglove Studio | Latest | foxglove.dev | Visualization |
| MoveIt 2 (optional) | Latest | ros.org | Planning/MoveIt |

---

## Interface

**Emits** — `/joint_states` (1 kHz, JointState for the three motors), `/platform_pose` (1 kHz, PoseStamped for the moving platform), `/robot_status` (1 Hz), `/tf`. Optional `/camera/image_raw` (30 Hz).<br>

**Accepts** — `/target_pose` (1 kHz, PoseStamped for the platform), `/joint_commands` (1 kHz, JointState for direct joint control), `/teleop_input` (20 Hz from gamepad, optional).<br>

**Serves** — `/enable`, `/disable`, `/calibrate`, `/home`, `/reset_odometry`.<br>

**Executes** — `/move_to` (action, move platform to target pose), `/pick_place` (action, full pick-and-place cycle), `/follow_trajectory` (action, follow a trajectory of waypoints).<br>

**Extensions** — `falcon/platform_position`, `falcon/motor_temps`, `falcon/motor_current`, `falcon/collision_detected`, `falcon/gripper_state`.<br>

**Frame conventions** — `base_link` at center of base plate. `platform_link` at center of moving platform. Motor frames: `motor_1`, `motor_2`, `motor_3`. Arm frames: `upper_arm_1`, `forearm_1`, and equivalent for arms 2 and 3. `tool0` at the end effector mounting point.<br>

**Units** — SI. Meters, meters/second, radians, seconds, Newtons, Newton-meters.

---

## Model

**URDF / Xacro** — `model/falcon.urdf.xacro`. Includes 3 revolute joints for the motors, 6 spherical joints for the elbow and wrist connections, and 3 fixed joints for the forearm links. Joint limits: motor angle range ±90°. Links: base, 3× upper arm, 3× forearm, platform, tool0.<br>

**SDF** — Used for Gazebo simulation.<br>

**Calibration** — Motor zero offsets (each motor's encoder zero set to mechanical zero). Arm link lengths measured from CAD. Base dimensions measured from CAD. Ball joint offsets. Platform mass and inertia. The inverse kinematics depends on accurate link lengths; calibration ensures the kinematic model matches the physical robot.<br>

**Dynamics** — Motor constants from AK80-9 datasheet: 48V nominal, 9:1 reduction, 24 N·m peak torque, 400 RPM max output speed. Arm link masses from carbon fiber tube weight. Platform mass from printed part. The parallel structure means the dynamics are coupled: the three arms interact through the platform. Inertia matrix computed from the URDF. Friction and damping identified through system identification.<br>

**Sensor transforms** — No external sensors on the base configuration. Optional camera mounted on the moving platform, pointing downward. Optional IMU on the base for vibration monitoring.<br>

**Collision geometry** — Simple cylinders for arm links in simulation. Sphere for the platform. Cylinders for the base frame.<br>

**Visual geometry** — STL meshes from printed and machined parts. Carbon fiber tubes modeled as cylinders.

---

## Trials

**Bench** — Motor direction, encoder counts, CAN bus communication with all three drives, inverse kinematics verification. Pass/fail, measured values, date. Expected: all three motors respond to position commands, encoders report position with sufficient resolution, inverse kinematics produces correct motor angles for a set of known target positions (verified by measuring the physical platform position with calipers).<br>

**Integration** — micro-ROS link at 921600 baud. ROS 2 bring-up with Cyclone DDS. Joint state publishing at 1 kHz. TF tree integrity verified. MoveIt 2 configuration (if used). Pass/fail, measured values, date.<br>

**Field** — Workspace verification: move platform to a grid of target positions and measure the actual position with a dial indicator. Repeatability test: move to the same position 100 times and measure the variation. Payload test: move a 0.5 kg and 1 kg payload through the workspace. Speed test: measure cycle time for a 300 mm vertical pick-and-place with 0.5 kg payload. Pass/fail, measured values, date.<br>

**Endurance** — Continuous pick-and-place cycles until motor temperature reaches 80 °C. Duty cycle and cycle time recorded.<br>

**Environmental** — Tested in indoor, controlled environment. Not for outdoor use. Not for explosive atmospheres.<br>

**Known limitations** — No rotation (3-DOF translation only). Workspace is smaller than a serial arm of equivalent reach. The parallel structure means the robot cannot reach around obstacles; the workspace is a direct projection below the base. Singularities exist at the edges of the workspace; the trajectory generator must avoid these regions. Calibration of link lengths and motor zero offsets is critical for accuracy; small errors in calibration produce large position errors at the platform.

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

**Next steps** — Finalise BOM, order components, CNC base plate and joint housings, cut carbon fiber tubes, assemble. Milestone 1: bench test all three motors and CAN communication. Milestone 2: inverse kinematics verification. Milestone 3: workspace and repeatability test. Milestone 4: pick-and-place cycle with 0.5 kg payload. Milestone 5: speed test and cycle time optimization. Milestone 6: optional camera and vision-guided pick-and-place. Milestone 7: optional 4-DOF delta with rotary axis.
