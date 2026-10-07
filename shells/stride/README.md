# stride

**Class:** exoskeleton<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Wearable bilateral lower-limb exoskeleton for gait rehabilitation and assistive walking. Four active degrees of freedom (bilateral hip and knee flexion/extension) and two passive ankle joints with spring mechanisms to counteract foot drop. Supports patients with locomotor dysfunction caused by stroke, spinal cord injury, traumatic brain injury, multiple sclerosis, and other central nervous system disorders. Enables overground walking, in-place walking, sit-to-stand, and standing training in the early stages of rehabilitation.<br>

**Environment** — Indoor clinical, rehabilitation, and research settings. Flat hard floors and low-pile carpet. Not for outdoor use, stairs, or uneven terrain. Operating temperature 10–35 °C. The device is worn by a human; all safety systems must be validated before any patient is placed in the device.<br>

**Mission** — Provide reproducible, high-repetition gait training for patients with lower-limb motor impairment. The exoskeleton imposes a physiologically correct gait pattern, inhibits abnormal gait formation, and allows the therapist to adjust stride length, step height, walking speed, and guidance force in real time. It exists to reduce the physical burden on therapists, standardise rehabilitation protocols, and enable patients to practice walking earlier and more intensively than they could with manual therapy alone.<br>

**Operator** — Two-person operation. A trained therapist or clinician wears the device with the patient and controls gait parameters via a touchscreen tablet. A second person (assistant or therapist) supports the patient and monitors safety. The device is not for unsupervised patient use.<br>

**Reusability** — Repeatable build from off-the-shelf and 3D-printed components. Based on the ExoMotus M4 architecture, an FDA-cleared and CE-marked rehabilitation exoskeleton manufactured by Fourier Intelligence. The open EXOPS platform system allows third-party integration.

---

## Spec

**Physical** — Exoskeleton weight 13 kg (double-leg configuration, including cuffs, sensor shoes, and batteries). Support frame weight 100 kg (balancing frame with wheels). Patient height range 150–190 cm. Patient weight range 40–100 kg. Adjustable upper leg length 34–49 cm, lower leg length 33–48 cm, hip width 27–41 cm (middle/wide configurations). Shoe size 23–30 cm in 1 cm increments. Overall dimensions at minimum adjustment: height 1,190 mm, width 480 mm (middle hip) or 520 mm (wide hip), depth 440 mm with 26 cm sensor shoes attached.<br>

**Kinematic** — 6 degrees of freedom total. 4 active DOF: bilateral hip flexion/extension and bilateral knee flexion/extension. 2 passive DOF: bilateral ankle joints with spring mechanisms to counteract foot drop. Hip range of motion: extension 20°, flexion 120°. Knee range of motion: extension 5°, flexion 120°. The kinematic chain follows the human lower-limb anatomy: pelvis → hip → thigh → knee → shank → ankle → foot. The exoskeleton is parallel to the human limb, not serial; the human's own joints are the reference, and the exoskeleton actuators apply torque about the same axes.<br>

**Dynamic** — Maximum assistive torque 40 N·m per joint (hip and knee). Walking speed 0.44–1.3 km/h, adjustable in 0.1 km/h increments. Stride length and step height adjustable. Guidance force adjustable. Continuous operating time approximately 1 hour per battery charge. The exoskeleton supports the patient's weight partially through the support frame; the exoskeleton itself does not need to bear the full body weight, only the torque required to move the limbs and the residual weight not carried by the frame.<br>

**Power** — Custom lithium battery. 40 V nominal (based on comparable active exoskeletons). Battery is carried on the support frame or the exoskeleton's hip module. Operating time approximately 1 hour continuous. Charging time not specified. The battery is swappable for extended sessions. Power distribution: 40 V to motor drivers, 24 V for control electronics, 5 V for sensors and interface. All power wiring sized for peak motor current (15–20 A).<br>

**Thermal** — 10–35 °C operating. Passive cooling. Motors are mounted at the hip and knee joints with aluminium heat sinks. Drivers report temperature; the control software derates torque if temperature exceeds 70 °C. The patient's body heat and the motor heat combine; thermal management is critical for patient comfort and safety.<br>

**Environmental** — Indoor, controlled clinical environment. Not IP-rated. Not for rain, dust, or outdoor use. The device must not be exposed to liquids.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $15,000–$25,000 for a research-grade build, or $5,000–$10,000 for a reduced-capability prototype.<br>

**Structure** — The exoskeleton frame is parallel to the human limb. The structural components are high-strength steel, aluminium, fabric, and plastic, as used in the ExoMotus M4. The hip module houses the hip actuators, the control electronics, and the battery. The thigh links connect the hip to the knee, with adjustable length to fit different upper leg lengths. The knee module houses the knee actuator and the thigh and shank cuffs. The shank links connect the knee to the ankle, with adjustable length. The ankle joint is passive, with a spring mechanism to counteract foot drop. The foot plate connects to the patient's shoe via the sensor shoe. The support frame is a separate structure with four low-friction wheels, a built-in seat, and a body-weight support system that allows the patient to practice walking without fear of falling. The support frame has a vertical degree of freedom (height adjustment) and a harness system to support the patient's torso. The overall design follows the ExoMotus M4, which incorporates an ergonomic balance frame and multiple harnesses for added safety.<br>

**Actuation** — 4 active joints (bilateral hip and knee) driven by brushless DC motors with harmonic or cycloidal reducers. The actuators must deliver up to 40 N·m peak torque per joint. The motors are positioned at the joints to minimise the transmission path and maximise torque density. The actuator design follows the variable stiffness actuator (VSA) approach used in lower-limb exoskeletons, which provides force and impedance controllability by adjusting the mechanical stiffness of the actuator. Alternatively, series elastic actuators (SEAs) can be used to provide compliant interaction and force sensing through deflection measurement. The ankle joints are passive, with a spring mechanism to assist dorsiflexion and prevent foot drop. The spring stiffness is selected to match the patient's residual ankle function; the spring can be swapped for different stiffness values.<br>

**Locomotion** — The exoskeleton does not locomote independently; it assists human walking. The gait cycle is generated by the control software, which drives the hip and knee joints through a physiologically correct trajectory. The patient's residual motor function is preserved: the exoskeleton provides only the assistance required to complete the movement, not the full torque. The guidance force parameter controls how much the exoskeleton assists versus how much the patient contributes. This is the key principle of rehabilitation exoskeletons: they should not replace the patient's movement, but augment it so the patient can practice a correct gait pattern.<br>

**Manipulation** — None. The exoskeleton is a wearable platform; it does not have manipulators. The end effectors are the foot plates, which connect to the patient's shoes.<br>

**Power system** — Custom 40 V lithium battery. The battery is carried in the hip module or on the support frame. 40 V direct to motor drivers. 24 V for control electronics. 5 V for sensors and the touchscreen. The support frame provides power to the exoskeleton via a cable when the patient is in the frame; the exoskeleton switches to battery power when the patient walks away from the frame (if supported by the configuration). The ExoMotus M4 is designed for overground walking with the support frame, so the exoskeleton may remain tethered to the frame for power and safety.<br>

**Wiring** — Motor power: 14 AWG. Motor signal: 26 AWG shielded. Sensor wiring: 26 AWG shielded. Emergency stop wiring: redundant, fail-safe. All wiring routed through the exoskeleton frame with service loops at joints. Cable management is critical to avoid pulling, pinching, or abrading cables as the patient moves. The wiring harness must be comfortable against the patient's body and must not cause pressure points.<br>

**Custom parts** — 3D-printed PA12-CF or PETG cuffs and brackets. Aluminium structural links (machined or waterjet). 3D-printed sensor shoe adapters. Custom PCBs for motor drivers and control electronics. The ExoMotus M4 uses steel, aluminium, fabric, and plastic in its construction.<br>

**Fasteners** — M4 and M5 stainless steel. M4 for cuff mounting and brackets. M5 for structural connections. All fasteners must be vibration-resistant and must not loosen during walking. Thread locker (blue) on all motor mount screws. Nylon insert lock nuts for vibration-prone connections.<br>

**Tools required** — 3D printer (PA12-CF capable), hex drivers (2.5 mm, 3 mm, 4 mm), soldering iron, wire crimper, multimeter, torque wrench, patient-fitting tools (measurement tape, adjustment jigs).

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| Brushless DC motor with harmonic/cycloidal reducer (hip) | 2 | Various | ~$500 each | Actuators/BLDC |
| Brushless DC motor with harmonic/cycloidal reducer (knee) | 2 | Various | ~$500 each | Actuators/BLDC |
| FOC motor driver board | 4 | ODrive / custom | ~$100 each | Actuators/driver |
| Magnetic encoder (AS5047P or equivalent) | 4 | AMS | ~$8 each | Sensors/Encoder |
| Torque sensor (joint-level, compact) | 4 | Various | ~$200 each | Sensors/Torque |
| Control PC (mini PC or Raspberry Pi 5) | 1 | Various | ~$80 | Compute/SBC |
| Teensy 4.0 (real-time control) | 1 | PJRC | ~$25 | Compute/MCU |
| BNO085 9-DOF IMU | 1 | Adafruit | ~$25 | Sensors/IMU |
| Touchscreen tablet (operator interface) | 1 | Various | ~$300 | Operator/Interface |
| 40 V lithium battery | 1 | Custom | ~$200 | Power/battery |
| 24 V and 5 V buck converters | 2 | Pololu | ~$20 each | Power/converter |
| Emergency stop button (latching) | 1 | Various | ~$30 | Safety/E-stop |
| Support frame with wheels, seat, harness | 1 | Custom | ~$3,000 | Structure/Frame |
| Aluminium structural links (hip, thigh, shank) | 1 set | Machined | ~$500 | Structure |
| 3D-printed PA12-CF cuffs and brackets | 1 set | Custom | ~$150 | Custom parts |
| Sensor shoes (force plates) | 2 | Custom | ~$300 each | Sensors/FootContact |
| Cables, connectors, fasteners | assorted | Various | ~$200 | Wiring/Fasteners |
| Patient harnesses and straps | 1 set | Various | ~$150 | Structure/Safety |
| **Total (research build)** | | | **~$15,000–$25,000** | |

---

## Systems

**Manifest** — See detailed manifest below.<br>

**Firmware** — Teensy 4.0 runs the real-time joint control loop at 1 kHz. It reads joint positions from magnetic encoders, joint torques from torque sensors, and patient gait phase from foot contact sensors. It runs a joint-space PD or impedance controller with gravity compensation and sends torque commands to the four motor drivers over CAN bus. It receives high-level gait parameters from the control PC over micro-ROS serial. The control PC runs Ubuntu 24.04 LTS and ROS 2 Jazzy, and hosts the user interface. The ExoMotus M4 uses a touchscreen interface for mode and parameter selection, and supports WiFi for future control via smart watch or tablet.<br>

**Middleware** — ROS 2 Jazzy. micro-ROS between Teensy 4.0 and the control PC over USB serial at 921600 baud. Cyclone DDS on the LAN for remote monitoring and data logging. The EXOPS open platform system allows third-party integration, and the architecture supports ROS 2 as the primary middleware.<br>

**Perception** — Joint encoders (magnetic, 14-bit) for joint position. Joint torque sensors for assistive torque measurement. Foot contact sensors (force-sensitive resistors or load cells in the sensor shoes) for gait phase detection. BNO085 IMU on the pelvis for trunk orientation and fall detection. The exoskeleton does not use external perception (cameras, LiDAR); its perception is entirely proprioceptive and patient-state-focused.<br>

**Control** — The control architecture is a two-level hierarchy. The high-level gait generator runs on the control PC at 100–200 Hz and produces joint trajectories for the hip and knee based on the selected gait pattern, walking speed, stride length, and step height. The low-level joint controller runs on the Teensy at 1 kHz and tracks the desired joint trajectories using PD or impedance control. The impedance control law allows the patient to deviate from the reference trajectory while the exoskeleton provides corrective torque to guide them back. The guidance force parameter scales the stiffness of this correction: high guidance force means the exoskeleton is stiff and imposes the trajectory; low guidance force means the exoskeleton is compliant and the patient has more freedom. The ExoMotus M4 supports training modes including walk on spot, walk on ground, sit, and stand. Automatic calibration adjusts the joint zero positions for each patient. Safety features include emergency stop, speed and position limits, and joint protection and overload protection.<br>

**Planning** — Gait trajectory generation is pre-computed from a library of gait patterns. The therapist selects the pattern and adjusts parameters (speed, stride length, step height, guidance force). The trajectory generator interpolates between waypoints and produces smooth joint trajectories that respect the patient's joint limits. There is no autonomous navigation or path planning; the patient is the navigator, and the exoskeleton assists their walking.<br>

**Learning** — None in the base platform. The gait patterns are pre-computed and clinically validated. Optional: the exoskeleton can log patient gait data (joint angles, torques, foot contacts) for post-session analysis and for adapting the gait pattern to the patient's progress over multiple sessions. The ExoMotus M4 allows therapists to personalise gait parameters to the patient's specific requirements.<br>

**Teleoperation** — The therapist controls the exoskeleton via a touchscreen tablet mounted on the support frame or held by the assistant. The interface allows mode selection (walk on spot, walk on ground, sit, stand), parameter adjustment (speed, stride length, step height, guidance force), and session management (start, stop, emergency stop). The ExoMotus M4 supports WiFi control for future expansion to smart watch or tablet control.<br>

**Safety** — This is the most safety-critical platform in the library. The patient is physically coupled to the exoskeleton; a control failure or mechanical failure can cause injury. Safety systems: (1) Hardware emergency stop button on the support frame and on the exoskeleton. (2) Software joint limits enforced in firmware and in the trajectory generator. (3) Torque limits per joint enforced in the motor drivers. (4) Speed and position limits. (5) Automatic calibration to prevent range-of-motion errors. (6) Joint protection and overload protection. (7) Fall detection via pelvis IMU: if trunk tilt exceeds 20°, the exoskeleton enters a damping mode and the support frame harness holds the patient. (8) The support frame with four low-friction wheels and a built-in seat provides a stable base and prevents falls. (9) Multiple harnesses secure the patient to the frame. (10) The device must comply with IEC 60601-1 (medical electrical equipment safety) and ISO 13482 (personal care robots) for clinical deployment.<br>

**Logging** — rosbag2 with MCAP format. Joint positions, velocities, torques, foot contacts, and IMU data recorded at 1 kHz. Gait parameters and session metadata recorded. Data format compatible with clinical gait analysis tools. The log is used for post-session review, patient progress tracking, and regulatory compliance.<br>

**Networking** — Ethernet or Wi-Fi via the control PC. Remote monitoring via SSH or a secure web interface. No cloud connectivity in the base platform; all patient data remains local for privacy and regulatory compliance.<br>

**Config files** — URDF (`stride.urdf.xacro`), joint limits and PID/impedance gains (`joint_params.yaml`), gait parameters (`gait_params.yaml`), safety limits (`safety_params.yaml`), patient profiles (per-patient calibration and parameter sets).<br>

**Launch files** — `bringup.launch.py`, `gait.launch.py`, `logging.launch.py`, `safety.launch.py`.<br>

**Dependencies** — ROS 2 Jazzy, `micro_ros_arduino`, `bno08x_driver`, `rosbag2`, `robot_state_publisher`, `rviz2` (for engineering monitoring), `can_msgs` for motor driver communication.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ROS 2 | Jazzy | ros.org | Middleware/ROS2 |
| Ubuntu | 24.04 LTS | ubuntu.com | OS/Linux |
| micro-ROS | Jazzy-compatible | microros.org | Middleware/microROS |
| bno08x_driver | Latest | index.ros.org | Perception/drivers |
| rosbag2 | Latest | ROS 2 | Logging/rosbag |
| robot_state_publisher | Latest | ROS 2 | Model/URDF |
| rviz2 | Latest | ROS 2 | Visualization |
| Foxglove Studio | Latest | foxglove.dev | Visualization |
| ODrive | Latest | odriverobotics.com | Firmware/FOC |

---

## Interface

**Emits** — `/joint_states` (1 kHz, JointState for hip and knee joints), `/joint_torques` (1 kHz, Float64MultiArray for assistive torques), `/foot_contacts` (100 Hz, custom message), `/imu/data` (100 Hz, Imu), `/gait_phase` (100 Hz, custom message), `/robot_status` (1 Hz).<br>

**Accepts** — `/gait_parameters` (20 Hz, custom message for speed, stride length, step height, guidance force), `/mode_command` (custom, for mode selection), `/teleop_input` (20 Hz from touchscreen).<br>

**Serves** — `/enable`, `/disable`, `/calibrate`, `/start_session`, `/end_session`.<br>

**Executes** — `/start_walking` (action), `/stop_walking` (action), `/sit` (action), `/stand` (action), `/walk_on_spot` (action).<br>

**Extensions** — `stride/patient_effort` (estimated from joint torque and trajectory tracking error), `stride/assist_level`, `stride/battery_state`, `stride/thermal_status`.<br>

**Frame conventions** — `pelvis` at the hip center. `hip_left`, `hip_right` at the hip joint axes. `knee_left`, `knee_right` at the knee joint axes. `ankle_left`, `ankle_right` at the ankle joints. `foot_left`, `foot_right` at the foot plates. The kinematic chain is pelvis → hip → thigh → knee → shank → ankle → foot for each leg.<br>

**Units** — SI. Meters, radians, seconds, Newtons, Newton-meters.

---

## Model

**URDF / Xacro** — `model/stride.urdf.xacro`. Includes 4 revolute joints (bilateral hip and knee) and 2 passive joints (bilateral ankle). Joint limits from mechanical design: hip extension 20°, hip flexion 120°, knee extension 5°, knee flexion 120°. Links: pelvis, 2× thigh, 2× shank, 2× foot. The URDF is used for engineering monitoring (RViz) and for simulation.<br>

**SDF** — Used for Gazebo simulation. Patient model optional for biomechanical simulation.<br>

**Calibration** — Joint zero offsets (each motor's encoder zero set to the mechanical zero corresponding to the patient's neutral standing pose). Automatic calibration routine adjusts zero positions for each patient. Torque sensor zero offsets. Foot contact sensor thresholds. IMU orientation and bias. Patient-specific calibration is stored in a patient profile and recalled for each session.<br>

**Dynamics** — Motor constants from datasheet. Reducer ratios from harmonic/cycloidal design. Link masses from CAD. The exoskeleton dynamics are coupled with the patient's limb dynamics; the combined system is a human-in-the-loop dynamic system. The controller must account for the patient's limb inertia, which varies with patient size and residual muscle tone. System identification is performed with the patient in the loop to tune the impedance controller. The assistive torque is computed from the desired joint trajectory and the measured joint position and torque, using an impedance control law.<br>

**Sensor transforms** — Joint encoders at each active joint. Torque sensors at each active joint. Foot contact sensors in the sensor shoes. IMU on the pelvis, 50 mm above the hip center. The sensor transforms are used to map from sensor frames to the joint frames for control and logging.<br>

**Collision geometry** — Simple boxes and cylinders for links in simulation. The exoskeleton is parallel to the human limb; collision checking must account for the human limb's volume to avoid the exoskeleton colliding with the patient.<br>

**Visual geometry** — STL meshes from printed and machined parts. Patient body model optional for visualisation.

---

## Trials

**Bench** — Motor direction, encoder counts, torque sensor calibration, IMU readings, foot contact sensors, emergency stop. Pass/fail, measured values, date. Expected: all four motors respond to torque commands, encoders report position with 14-bit resolution, torque sensors read zero at rest and linear response under load, IMU reports pelvis orientation within 2° accuracy, foot contact sensors trigger on ground contact, emergency stop halts all motion within 100 ms.<br>

**Integration** — micro-ROS link at 921600 baud. ROS 2 bring-up with Cyclone DDS. Joint state publishing at 1 kHz. Gait trajectory generation and tracking. Impedance controller tuning. Pass/fail, measured values, date.<br>

**Field** — Phantom walking test (exoskeleton worn by a healthy engineer, not a patient) to verify gait trajectory, speed range, and safety limits. Sit-to-stand test. Stand test. Walk-on-spot test. Overground walking test at 0.44 km/h and 1.3 km/h. Guidance force sweep from 0% to 100%. Pass/fail, measured values, date.<br>

**Endurance** — Continuous walking until battery cutoff at 3.3 V per cell. Expected runtime: ~1 hour. Motor temperature at end (expected <70 °C with derating if exceeded). Patient comfort assessment (pressure points, cuff fit, harness comfort).<br>

**Environmental** — Tested in indoor clinical and laboratory environments only. Not for outdoor use.<br>

**Known limitations** — Requires a trained therapist or clinician to operate; the device is not for unsupervised patient use. Setup time is approximately 5 minutes with practice. The exoskeleton is 13 kg, which adds to the patient's load; the support frame carries part of this, but the patient still bears some of the weight. The ankle joints are passive; the device does not provide active ankle assistance. Walking speed is limited to 1.3 km/h, which is slower than normal walking (approximately 5 km/h). The support frame occupies floor space and requires a flat surface. Regulatory clearance (FDA, CE) is required for clinical use; the device as described is a research platform and is not certified for clinical deployment.

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

**Next steps** — Finalise BOM, order components, machine structural links, print cuffs and brackets, assemble. Milestone 1: bench test all four motors, torque sensors, and encoders. Milestone 2: stand and sit with the support frame and a healthy test subject. Milestone 3: walk-on-spot with gait trajectory tracking. Milestone 4: overground walking with guidance force control. Milestone 5: safety validation (emergency stop, fall detection, torque limits). Milestone 6: clinician training and protocol development. Milestone 7: regulatory consultation (FDA 510(k) or CE marking pathway) if clinical deployment is intended.

---

**Note on this Shell:** The exoskeleton is the only platform class in the library that is physically coupled to a human. This changes every engineering decision: safety systems are not optional, failure modes can injure the patient, and the control system must cooperate with the human rather than replace them. The ExoMotus M4 is the reference platform for this Shell; it is FDA-cleared (HAL-ML05 and HAL-ML07 have FDA 510(k) clearance) and CE-marked under MDR (EU) 2017/745 for the HAL-ML07 and HAL-ML08. The ExoMotus M4 itself is deployed in hospitals and rehabilitation centres in the UK, Shanghai, Singapore, and the Philippines. The engineering principles demonstrated here — parallel kinematics, impedance control, support frame design, and patient-in-the-loop calibration — apply to any wearable exoskeleton platform.
