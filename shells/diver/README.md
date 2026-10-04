# diver

**Class:** aquatic<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-10-04

---

## Identity

**Role** — Small observation-class remotely operated underwater vehicle (ROV) for teleoperated inspection, exploration, and object recovery in shallow to medium-depth water. Holds a camera and thrusters, dives to depth, maneuvers in 6 degrees of freedom, and relays live video and telemetry to a surface operator via tether.<br>
**Environment** — Freshwater and saltwater. Pools, lakes, rivers, harbors, shallow coastal. Max depth 100 m. Water temperature 0–35 °C. Not for deep-sea or high-current environments.<br>
**Mission** — Teleoperated underwater inspection of hulls, pipelines, dams, and structures. Search and recovery. Environmental monitoring. Scientific observation. The ROV is not autonomous; the operator sees through the camera and drives.<br>
**Operator** — Single operator at the surface via tether-connected control station. Live video feed and telemetry to a laptop or monitor. Gamepad or joystick control.<br>
**Reusability** — Repeatable build from off-the-shelf and 3D-printed components. Production candidate. Many parts are shared with the BlueROV2 ecosystem.

---

## Spec

**Physical** — Target 4.5 kg in air, slightly positively buoyant in water (approximately 50 g positive). 450 × 350 × 250 mm frame. 6-thruster configuration (4 horizontal, 2 vertical). Watertight electronics enclosure. Center of buoyancy above center of mass for passive stability.<br>

**Kinematic** — 6 degrees of freedom: surge, sway, heave, roll, pitch, yaw. 4 horizontal thrusters in vector configuration for surge, sway, and yaw. 2 vertical thrusters for heave. Roll and pitch are passively stabilized by buoyancy.<br>

**Dynamic** — Max forward speed ~1.5 m/s. Max depth 100 m (limited by enclosure and tether). Payload capacity 1 kg (additional sensors or small manipulator). Thrust per thruster ~2.5 kgf at 16V. Total horizontal thrust ~10 kgf, vertical thrust ~5 kgf.<br>

**Power** — 16V nominal from surface power supply via tether. 25 A max current draw. 400 W max power. Alternatively, onboard 4S LiPo (14.8V, 10 Ah) for untethered short-duration operation. Tether carries power and data.<br>

**Thermal** — Water-cooled by environment. Electronics enclosure dissipates heat through aluminum walls into surrounding water. No active cooling needed. Operating temperature 0–35 °C water.<br>

**Environmental** — IP68 (submersible) for all watertight components. Depth-rated to 100 m. Not for high-current, low-visibility, or contaminated water without additional filtration.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $1,800–$2,500.<br>

**Structure** — HDPE or acrylic frame plates (waterjet or CNC cut). 3D-printed PETG or PA12-CF mounts for thrusters, enclosure, and camera. The frame is open (not enclosed) to allow water flow through. The watertight enclosure houses all electronics. Buoyancy foam is added to achieve neutral buoyancy. The design follows the BlueROV2 open-source architecture, which is a widely used reference platform for observation-class ROVs.<br>

**Actuation** — 6× brushless underwater thrusters. Selected thruster: T200 thruster (Blue Robotics) or equivalent. The T200 uses a brushless motor with a proprietary watertight seal and a 3-blade propeller. It produces 2.5 kgf forward thrust at 16V and 5.1 kgf at 20V (peak). It is designed for continuous underwater operation and is depth-rated to 300 m. Each thruster is paired with an ESC (electronic speed controller) inside the watertight enclosure. The ESC: Blue Robotics Basic ESC or a BLHeli_S equivalent, running SimonK or BLHeli firmware, controlled via PWM or DShot.<br>

**Locomotion** — 6-thruster vectored configuration. 4 horizontal thrusters angled at 45° for omnidirectional horizontal movement. 2 vertical thrusters for depth control. This configuration is standard for observation-class ROVs and provides full 6-DOF control.<br>

**Manipulation** — None initially. Optional small gripper (e.g., Blue Robotics Newton Gripper) can be mounted on the front for object recovery.<br>

**Power system** — 16V surface power supply (e.g., 16.8V 25A AC-DC adapter) via tether. Power is distributed to ESCs and electronics through the watertight enclosure. Alternatively, onboard 4S LiPo 10 Ah for untethered operation (shorter runtime, ~30–60 min).<br>

**Wiring** — Tether: Fathom Slim ROV tether (Blue Robotics) or equivalent. 4 mm diameter, neutrally buoyant, 100 m length. Carries 2× 18 AWG power conductors and 2× twisted pair for data (Ethernet or serial). The tether connects to the Fathom X tether interface board inside the enclosure, which provides Ethernet over the twisted pair.<br>

**Custom parts** — 3D-printed thruster mounts (PETG or PA12-CF). 3D-printed camera mount (PETG). 3D-printed enclosure end caps (PETG or machined aluminum). 3D-printed buoyancy foam mounts (PETG). 3D-printed tether strain relief (TPU).<br>

**Fasteners** — M3 and M4 stainless steel (316 marine grade for saltwater). M3 for electronics and brackets. M4 for structural connections. All fasteners are stainless steel to resist corrosion in saltwater.<br>

**Tools required** — Hex drivers (2 mm, 2.5 mm, 3 mm), soldering iron, wire crimper, multimeter, PVC cement for enclosure end caps (if using PVC), torque wrench for enclosure bolts.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| Blue Robotics T200 thruster | 6 | Blue Robotics | ~$200 each | Actuators/Thruster |
| Blue Robotics Basic ESC | 6 | Blue Robotics | ~$25 each | Actuators/ESC |
| Watertight enclosure, 4" acrylic tube, 300 mm | 1 | Blue Robotics | ~$150 | Enclosure |
| Aluminum end cap, 4" | 2 | Blue Robotics | ~$40 each | Enclosure |
| O-ring seals for end caps | 4 | Blue Robotics | ~$5 each | Enclosure |
| Cable penetrators (potting or compression) | 8 | Blue Robotics | ~$10 each | Enclosure |
| Fathom X tether interface | 1 | Blue Robotics | ~$100 | Comms/Tether |
| Fathom Slim tether, 100 m | 1 | Blue Robotics | ~$300 | Comms/Tether |
| Raspberry Pi 4 or 5 | 1 | Raspberry Pi | ~$80 | Compute/SBC |
| Raspberry Pi Camera Module 3 (or low-light camera) | 1 | Raspberry Pi | ~$25 | Sensors/Camera |
| PWM driver board (PCA9685) | 1 | Adafruit | ~$15 | Control/PWM |
| BNO085 IMU | 1 | Adafruit | ~$25 | Sensors/IMU |
| MS5837-30BA pressure sensor | 1 | Blue Robotics | ~$50 | Sensors/Depth |
| 16V 25A AC-DC power supply | 1 | Various | ~$60 | Power/Supply |
| 4S LiPo 10 Ah (optional untethered) | 1 | Various | ~$80 | Power/Battery |
| HDPE frame plates, 6 mm, cut | 2 | Local machine shop | ~$40 | Frame/plate |
| Buoyancy foam (ROV-grade) | 1 block | Blue Robotics | ~$30 | Buoyancy |
| Stainless steel M3/M4 fasteners | assorted | McMaster | ~$30 | Fasteners |
| PETG filament | ~500 g | Prusament | ~$25 | Custom parts |
| TPU filament | ~100 g | Prusament | ~$10 | Custom parts |
| Watertight cable glands | 4 | Various | ~$10 | Enclosure |
| Silicone grease for O-rings | 1 tube | Various | ~$10 | Enclosure |
| Surface control station: laptop + gamepad | 1 | Various | ~$200 | Operator interface |

---

## Systems

**Manifest** — See detailed manifest below.<br>

**Firmware** — Raspberry Pi 4 or 5 runs the onboard software. Arduino or Teensy microcontroller (optional) for PWM generation to ESCs. The Raspberry Pi runs a Python or C++ control loop that translates desired thrust vectors into PWM commands for each of the 6 ESCs. The Blue Robotics Basic ESC runs BLHeli_S or SimonK firmware and accepts standard RC PWM input (1000–2000 µs).<br>

**Middleware** — ROS 2 Jazzy on the Raspberry Pi. MAVLink or custom UDP protocol over the tether for communication with the surface. For simple operation, a Python script on the Pi receives UDP commands from the surface and outputs PWM to the ESCs. For advanced operation, ROS 2 runs on both the Pi and the surface station, with `ros2_control` managing the thrusters and `robot_localization` fusing the IMU and pressure sensor.<br>

**Perception** — Raspberry Pi Camera Module 3 for live video. Low-light camera preferred for deep or murky water (e.g., Arducam IMX477 with wide-angle lens). MS5837-30BA pressure sensor for depth measurement (±0.2 m accuracy, 30 bar rated, equivalent to 300 m depth). BNO085 IMU for orientation. Optional: Ping360 scanning sonar or Ping Sonar altimeter for obstacle detection and altitude hold.<br>

**Control** — The Raspberry Pi runs a thruster allocation algorithm that converts desired surge, sway, heave, roll, pitch, and yaw into individual thruster commands. This is the inverse of the thruster configuration matrix. For a 6-thruster vectored configuration, the allocation matrix is well-defined. PID controllers for depth hold and heading hold. The Blue Robotics Basic ESC accepts PWM at 50 Hz. Alternatively, DShot can be used for lower latency and digital communication.<br>

**Planning** — No autonomous navigation in the initial build. Optional: waypoint navigation using depth and heading hold. Optional: sonar-based obstacle avoidance.<br>

**Learning** — None initially. Teleoperation data (thruster commands, depth, heading, video) can be logged for future policy training.<br>

**Teleoperation** — Surface laptop or control station connected via Ethernet over the tether. A gamepad (e.g., Xbox controller) connected to the surface laptop provides operator input. A Python or ROS 2 node on the surface reads the gamepad and sends thruster commands over UDP or MAVLink to the onboard Raspberry Pi. Video is streamed from the Pi to the surface via RTSP or WebRTC over the tether Ethernet.<br>

**Safety** — Watchdog: if no command received within 500 ms, all thrusters stop. Depth limit: if pressure sensor reads >100 m, thrusters are disabled and the ROV is commanded to ascend. Leak detection: optional humidity sensor inside the enclosure triggers a warning on the surface if water ingress is detected. Tether strain relief prevents pull on the enclosure penetrators.<br>

**Logging** — rosbag2 with MCAP format if using ROS 2. Otherwise, CSV or binary log of depth, heading, thruster commands, and timestamps. Video recorded on the surface station. Data format compatible with LeRobot for future policy training.<br>

**Networking** — Ethernet over the Fathom X tether interface. The Fathom X converts Ethernet to a twisted-pair signal that travels up the tether. At the surface, a matching Fathom X converts back to Ethernet. This provides a 100 Mbps link between the surface and the ROV. The Raspberry Pi connects to the Fathom X via Ethernet. Video and telemetry share this link.<br>

**Config files** — Thruster allocation matrix, PID gains for depth and heading, tether interface config, camera settings.<br>

**Launch files** — `bringup.launch.py`, `teleop.launch.py`, `logging.launch.py`.<br>

**Dependencies** — ROS 2 Jazzy (optional), `ms5837` driver, `bno08x_driver`, `joy`, `rosbag2`, `robot_state_publisher`, `rviz2` (optional), `cv_bridge` for camera, `gstreamer` or `ffmpeg` for video streaming.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ROS 2 | Jazzy | ros.org | Middleware/ROS2 |
| Ubuntu | 24.04 LTS | ubuntu.com | OS/Linux |
| ms5837 | Latest | Blue Robotics | Perception/drivers |
| bno08x_driver | Latest | index.ros.org | Perception/drivers |
| joy | Latest | ROS 2 | Teleoperation/input |
| rosbag2 | Latest | ROS 2 | Logging/rosbag |
| robot_state_publisher | Latest | ROS 2 | Model/URDF |
| rviz2 | Latest | ROS 2 | Visualization |
| Foxglove Studio | Latest | foxglove.dev | Visualization |
| gstreamer | Latest | gstreamer.freedesktop.org | Video streaming |
| OpenCV | Latest | opencv.org | Video processing |

---

## Interface

**Emits** — `/depth` (10 Hz, Float32 from MS5837), `/imu/data` (100 Hz, Imu), `/camera/image_raw` (30 Hz, Image), `/thruster_feedback` (10 Hz, thruster PWM values), `/robot_status` (1 Hz, battery/depth/temperature), `/tf`.<br>

**Accepts** — `/cmd_vel` (20 Hz, Twist for surge/sway/yaw), `/cmd_heave` (20 Hz, Float32 for vertical thrust), `/teleop_input` (20 Hz from gamepad).<br>

**Serves** — `/enable`, `/disable`, `/calibrate`, `/hold_depth` (action, hold current depth), `/hold_heading` (action, hold current heading).<br>

**Executes** — `/dive_to_depth` (action), `/hold_position` (action, depth + heading), `/return_to_surface` (action, ascend to 0 m depth).<br>

**Extensions** — `diver/leak_status`, `diver/tether_tension`, `diver/buoyancy_status`, `diver/sonar_altitude` (if sonar fitted).<br>

**Frame conventions** — `base_link` at ROV center. `base_footprint` at ROV bottom. `camera_link` at camera mount. `imu_link` at IMU position. `depth_link` at pressure sensor. `thruster_1` through `thruster_6` for thruster frames.<br>

**Units** — SI. Meters, meters/second, radians, seconds, bar for pressure.

---

## Model

**URDF / Xacro** — `model/diver.urdf.xacro`. Includes 6 thruster joints (continuous), IMU link, camera link, pressure sensor link. Thruster allocation matrix documented in config.<br>

**SDF** — Used for Gazebo simulation with underwater physics plugins (UUV Simulator or DAVE).<br>

**Calibration** — Thruster direction and PWM range (1000–2000 µs). IMU orientation and bias. Pressure sensor offset (surface pressure = 0 m). Camera intrinsics from checkerboard calibration in air (water refraction not corrected; underwater calibration recommended for precise measurements).<br>

**Dynamics** — Thruster thrust curves from Blue Robotics datasheet: 2.5 kgf at 16V forward, 2.0 kgf reverse. Drag coefficients estimated from CAD or identified through pool testing. Buoyancy calculated from displaced volume. Added mass and damping coefficients for underwater dynamics identified through system identification.<br>

**Sensor transforms** — IMU at ROV center, 20 mm above base. Camera at front, 50 mm forward, 50 mm height, 0° tilt. Pressure sensor at bottom of enclosure.<br>

**Collision geometry** — Simple boxes for frame and enclosure in simulation.<br>

**Visual geometry** — Frame mesh, thruster meshes, enclosure mesh.

---

## Trials

**Bench** — Thruster direction and PWM range. IMU readings. Pressure sensor reading (surface = 0 m). Camera feed. Leak test (pressurize enclosure to 1.5 bar and check for leaks). Pass/fail, measured values, date. Expected: all 6 thrusters respond to PWM commands, IMU reports orientation within 2° accuracy, pressure sensor reads 0 m at surface and increases linearly with depth, camera feed is clear.<br>

**Integration** — Tether interface connection. Ethernet link over tether at 100 Mbps. UDP command latency measured. Video stream latency measured. Thruster allocation verification. Pass/fail, measured values, date.<br>

**Field** — Pool test: depth control, heading control, surge/sway/yaw. Open water test: depth to 10 m, 20 m, 50 m. Tether management. Buoyancy verification. Pass/fail, measured values, date.<br>

**Endurance** — Continuous operation until surface power supply thermal limit or tether strain limit. Motor temperature (water-cooled, expected <40 °C).<br>

**Environmental** — Tested in freshwater pool and shallow saltwater. Depth-rated to 100 m. Not tested beyond 100 m.<br>

**Known limitations** — Tether limits range and maneuverability. No autonomous navigation. Camera performance degrades in low light and turbid water. No manipulator in base configuration. Depth limited to 100 m by enclosure and tether. Not for high-current environments.

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

**Next steps** — Finalise BOM, order components, assemble frame, wire electronics. Milestone 1: bench test thrusters and sensors. Milestone 2: pool test with tether. Milestone 3: open water test to 20 m. Milestone 4: depth hold and heading hold. Milestone 5: optional sonar and manipulator.
