# Rover

**Class:** wheeled<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-09-25

---

## Identity

**Role** — Small indoor differential-drive rover for teleoperated inspection and 2D mapping. Holds a 2D LiDAR and depth camera, navigates indoor spaces, and relays sensor data to a single operator.<br>
**Environment** — Indoor, flat floors, benign conditions. Wood, tile, concrete, low-pile carpet. Not for stairs, outdoor terrain, or wet surfaces.<br>
**Mission** — Teleoperated driving, real-time 2D mapping with SLAM, obstacle detection, and camera inspection. Optional waypoint navigation via Nav2.<br>
**Operator** — Single operator via Wi-Fi. Supervised autonomy for waypoint following and map-based navigation.<br>
**Reusability** — Repeatable build from off-the-shelf components. Production candidate for research.

---

## Spec

**Physical** — Target 4.5 kg all-up weight (AUW). 350 × 300 × 250 mm footprint. 20×20 mm aluminum extrusion frame with PETG 3D-printed brackets. Ground clearance 25 mm. Center of mass is low, positioned over the drive axle.<br>
**Kinematic** — Differential drive, 2 powered wheels, 2 passive casters. Wheel diameter 100 mm. Track width 280 mm. Max speed 0.8 m/s. Zero-turn radius.<br>
**Dynamic** — Payload capacity 2 kg (sensor payload). Max incline 5°. Stall torque per motor ~2 Nm.<br>
**Power** — 12V 5000 mAh Li-ion pack (3S4P 18650). 55.5 Wh. Runtime 3–4 hours typical at moderate driving. XT60 connector. 5V/5A buck converter for Raspberry Pi 5, 12V direct for motors, 5V/3A buck for sensors.<br>
**Thermal** — 10–35 °C operating. Passive cooling. Raspberry Pi 5 requires the active cooler for sustained loads; without it, thermal throttling occurs above ~60 °C.<br>
**Environmental** — Indoor only. Not IP-rated. No dust protection beyond basic covers.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $950–$1,200.<br>
**Structure** — 20×20 mm aluminum extrusion frame, cut to length. 3 mm aluminum base plate for electronics. 3D-printed PETG brackets for motor mounts, caster mounts, LiDAR tower, and electronics tray. TPU camera mount for vibration damping.<br>
**Actuation** — 2× Pololu 37D metal gearmotors, 12V, with 64 CPR encoders. The selected gear ratio is 19:1, giving a no-load speed of 530 RPM at 12V. Stall current is 5.5 A per motor, stall torque is 8.5 kg·cm (0.83 Nm) at the gearbox output. The encoder provides 64 counts per revolution of the motor shaft and 1200 CPR of the gearbox output shaft.<br>
**Locomotion** — Differential drive. Two powered wheels. Two passive swivel casters (50 mm) for stability.<br>
**Manipulation** — None. Sensor payload only.<br>
**Power system** — 12V 5000 mAh Li-ion, XT60 connector. 5V 5A buck converter for compute. 5V 3A buck converter for sensors. The Raspberry Pi 5 requires a 5V/5A supply for optimal performance; the official power supply provides this via USB-C with Power Delivery.<br>
**Wiring** — 18 AWG for motor power, 22 AWG for sensor power, 26 AWG for signal. JST-XH and JST-SH connectors for sensors. Motor connections are screw terminals on the Cytron MDD10A.<br>
**Custom parts** — Motor mounts (3D printed PETG, 40% infill), caster mounts (3D printed PETG), LiDAR tower (3D printed PETG, 150 mm height), camera mount (3D printed TPU for damping), electronics tray (3D printed PETG).<br>
**Fasteners** — M3 and M4 stainless steel. M3 for electronics and brackets. M4 for structural connections to the extrusion.<br>
**Tools required** — Hex drivers (2 mm, 2.5 mm, 3 mm), soldering iron, wire cutters, multimeter, crimping tool for JST connectors, M3/M4 tap set for extrusion.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| 20×20 mm aluminum extrusion, 1 m lengths | 3 | Misumi / 80/20 | ~$30 | Frame/extrusion |
| 3 mm aluminum base plate, 300×250 mm | 1 | SendCutSend / local | ~$25 | Frame/plate |
| Pololu 37D 19:1 gearmotor 12V with 64 CPR encoder | 2 | Pololu | ~$80 | Actuators/DC |
| 100 mm rubber wheel, 6 mm D-shaft | 2 | Pololu | ~$20 | Locomotion/wheel |
| Swivel caster, 50 mm | 2 | Hardware store | ~$10 | Locomotion/caster |
| Cytron MDD10A dual motor driver | 1 | Cytron | ~$25 | Actuators/driver |
| Teensy 4.0 | 1 | PJRC | ~$25 | Compute/MCU |
| Raspberry Pi 5, 8 GB | 1 | Raspberry Pi | ~$80 | Compute/SBC |
| Raspberry Pi 5 active cooler | 1 | Raspberry Pi | ~$5 | Compute/cooling |
| 128 GB NVMe SSD + M.2 HAT | 1 | Various | ~$40 | Compute/storage |
| RPLIDAR A1M8 | 1 | Slamtec | ~$99 | Sensors/LiDAR |
| Intel RealSense D435i | 1 | Intel | ~$350 | Sensors/camera |
| BNO085 IMU (Adafruit breakout) | 1 | Adafruit | ~$25 | Sensors/IMU |
| 12V 5000 mAh Li-ion pack | 1 | Various | ~$60 | Power/battery |
| 5V 5A buck converter | 1 | Pololu | ~$15 | Power/converter |
| 5V 3A buck converter | 1 | Pololu | ~$8 | Power/converter |
| XT60 connector pair | 1 | Various | ~$3 | Power/connector |
| JST-XH, JST-SH connector kits | 1 each | Various | ~$20 | Wiring/connectors |
| 18/22/26 AWG silicone wire | assorted | Various | ~$20 | Wiring |
| M3, M4 stainless screws and standoffs | assorted | McMaster | ~$30 | Fasteners |
| 3D printing filament (PETG, TPU) | ~500 g | Prusament | ~$25 | Custom parts |

---

## Systems

**Manifest** — See detailed manifest below.<br>
**Firmware** — Teensy 4.0 runs motor control loop at 50 Hz (encoder read, IMU read, motor PID) over micro-ROS. Raspberry Pi 5 runs ROS 2 Jazzy on Ubuntu 24.04 LTS.<br>
**Middleware** — ROS 2 Jazzy. micro-ROS between Teensy 4.0 and Raspberry Pi 5 over USB serial. Cyclone DDS on the LAN for remote visualization and teleoperation.<br>
**Perception** — RPLIDAR A1M8 provides 360° 2D scan at up to 8000 Hz sample rate. Working range 0.15–12 m, with accuracy of ≤1% of actual distance at <3 m, ≤2% at 3–5 m, and ≤2.5% at 5–25 m. Angular resolution ≤1°. The RealSense D435i provides depth and RGB. Depth range 0.1–10 m, depth error under 2% at 2 m, FOV 87°×58°, with an integrated 6-DOF IMU. The BNO085 provides 9-DOF orientation with fused output at up to 1 kHz. It integrates a triaxial 12-bit accelerometer (±8g), a triaxial 16-bit gyroscope (±2000°/s), and a triaxial magnetometer, running CEVA's SH-2 firmware on an ARM Cortex-M0+.<br>
**Control** — PID velocity control per wheel on Teensy at 50 Hz. Differential drive kinematics computed on Raspberry Pi 5. Motor commands sent from Pi to Teensy via micro-ROS topics. The Cytron MDD10A accepts PWM speed control up to 20 kHz and supports sign-magnitude operation.<br>
**Planning** — Nav2 stack for waypoint navigation and obstacle avoidance. SLAM Toolbox for real-time 2D graph-based mapping and localization. Both are actively used on ROS 2 Jazzy with Raspberry Pi 5 as the primary compute platform.<br>
**Learning** — None initially. Teleoperation data (cmd_vel, odometry, scan, camera) can be logged in LeRobot-compatible format for future policy training.<br>
**Teleoperation** — ROS 2 `teleop_twist_keyboard` over Wi-Fi for keyboard control, or `joy` node with a gamepad. Latency target <100 ms end-to-end for local Wi-Fi.<br>
**Safety** — Software e-stop via ROS 2 service. Watchdog on motor commands (stops motors if no command received within 500 ms). Velocity limits enforced on Teensy. Obstacle stop via LiDAR: if any scan point is within 200 mm in the forward arc, motors are commanded to zero.<br>
**Logging** — rosbag2 with MCAP format. Full sensor suite recorded: `/scan` (10 Hz), `/camera/color/image_raw` (30 Hz), `/camera/depth/points` (30 Hz), `/imu/data` (100 Hz), `/odom` (50 Hz).<br>
**Networking** — Wi-Fi 6 via Raspberry Pi 5 onboard. SSH over Tailscale for secure remote access.<br>
**Config files** — Nav2 params (`nav2_params.yaml`), SLAM Toolbox params (`slam_params.yaml`), motor PID gains (micro-ROS params), URDF (`rover.urdf.xacro`), micro-ROS agent config.<br>
**Launch files** — `bringup.launch.py`, `teleop.launch.py`, `mapping.launch.py`, `navigation.launch.py`.<br>
**Dependencies** — ROS 2 Jazzy, Nav2, SLAM Toolbox, `realsense2_camera` (installable via `apt`), `rplidar_ros`, `bno08x_driver`, `micro_ros_arduino`, `teleop_twist_keyboard`, `joy`, `robot_localization` (EKF fusion of wheel odom + IMU).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ROS 2 | Jazzy | ros.org | Middleware/ROS2 |
| Ubuntu | 24.04 LTS | ubuntu.com | OS/Linux |
| micro-ROS | Jazzy-compatible | microros.org | Middleware/microROS |
| Nav2 | Jazzy branch | github | Planning/Nav2 |
| SLAM Toolbox | Jazzy branch | github | StateEstimation/SLAM |
| realsense2_camera | Latest | github | Perception/drivers |
| rplidar_ros | Latest | github | Perception/drivers |
| bno08x_driver | Latest | index.ros.org | Perception/drivers |
| joy | Latest | ROS 2 | Teleoperation/input |
| teleop_twist_keyboard | Latest | ROS 2 | Teleoperation/input |
| rosbag2 | Latest | ROS 2 | Logging/rosbag |
| robot_localization | Latest | ROS 2 | StateEstimation/fusion |
| diff_drive_controller | Latest | ros2_control | Control/differential |
| robot_state_publisher | Latest | ROS 2 | Model/URDF |
| rviz2 | Latest | ROS 2 | Visualization |
| Foxglove Studio | Latest | foxglove.dev | Visualization |

---

## Interface

**Emits** — `/scan` (10 Hz, LaserScan), `/camera/color/image_raw` (30 Hz, Image), `/camera/depth/points` (30 Hz, PointCloud2), `/imu/data` (100 Hz, Imu), `/odom` (50 Hz, Odometry), `/tf`, `/joint_states`, `/robot_status` (1 Hz).<br>
**Accepts** — `/cmd_vel` (20 Hz, Twist), `/teleop_input` (20 Hz).<br>
**Serves** — `/enable`, `/disable`, `/calibrate`, `/home`, `/reset_odometry`.<br>
**Executes** — `/navigate_to_pose` (Nav2 action), `/follow_waypoints` (Nav2 action).<br>
**Extensions** — `rover/lidar_health`, `rover/motor_temps`, `rover/battery_state`.<br>
**Frame conventions** — `base_link` → `base_footprint`, `laser`, `camera_link`, `imu_link`, `wheel_left_link`, `wheel_right_link`. The `base_footprint` is at ground level, `base_link` is at the chassis center.<br>
**Units** — SI. Meters, meters/second, radians, seconds.

---

## Model

**URDF / Xacro** — `model/rover.urdf.xacro`. Includes differential drive plugin for Gazebo, LiDAR, camera, IMU links.<br>
**SDF** — Used for Gazebo Harmonic simulation.<br>
**Calibration** — Wheel separation (280 mm), wheel radius (50 mm), encoder ticks per revolution (1200 CPR at output shaft). Camera intrinsics from 8×10 checkerboard. IMU bias and orientation. LiDAR mounting offset (200 mm height, centered).<br>
**Dynamics** — Motor constants from Pololu datasheet: 12V nominal, 530 RPM no-load, 5.5 A stall, 8.5 kg·cm stall torque. Gear ratio 18.75:1. Wheel friction and chassis mass (4.5 kg) identified through step response.<br>
**Sensor transforms** — LiDAR at 200 mm height, centered. Camera at 250 mm height, 10° down tilt, 50 mm forward of chassis center. IMU at chassis center, 30 mm above base plate.<br>
**Collision geometry** — Simple boxes for chassis and wheels in simulation.<br>
**Visual geometry** — Chassis mesh, wheel meshes, sensor meshes.

---

## Trials

**Bench** — Motor direction, encoder counts, IMU readings, LiDAR spin, camera feed. Pass/fail, measured values, date. Expected encoder resolution: 1200 CPR at output shaft = 1200 counts per wheel revolution. At 100 mm wheel diameter, that is 314 mm per revolution, giving 0.26 mm per count.<br>
**Integration** — micro-ROS link at 115200 baud over USB serial. ROS 2 bring-up with Cyclone DDS. Teleop latency measured end-to-end. TF tree integrity verified. Pass/fail, measured values, date.<br>
**Field** — Drive test on tile, wood, and low-pile carpet. Odometry drift measurement over 10 m straight line. SLAM map quality assessed against floor plan. Pass/fail, measured values, date.<br>
**Endurance** — Continuous drive until battery cutoff at 3.3V per cell. Motor temperature at end (expected <60 °C).<br>
**Environmental** — Tested on flat indoor surfaces only.<br>
**Known limitations** — No outdoor capability. No stair climbing. Odometry drifts without LiDAR correction. Camera depth limited to 3 m indoors due to IR interference. RPLIDAR A1M8 is indoor-only (no sunlight tolerance).

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
**Next steps** — Finalise BOM, order components, begin assembly. Milestone 1: teleoperated driving with LiDAR and camera feed. Milestone 2: SLAM mapping. Milestone 3: Nav2 waypoint following. Milestone 4: data logging for future learning.
