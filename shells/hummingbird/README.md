# Hummingbird

**Class:** aerial<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-09-23

---

## Identity

**Role** — Small efficient quadcopter for hover-precision teleoperated inspection and observation. It exists to hold a stable position in the air, look at something with a camera, and relay that view and its own state back to a single operator on the ground.<br>
**Environment** — Indoor and calm outdoor, close range, benign conditions. Not for rain, high wind, or GPS-denied environments beyond optical flow range. Operating temperature 10–35 °C. No IP rating; it is not sealed.<br>
**Mission** — Hover in place, observe, relay video and telemetry to the operator. Optional waypoint navigation via GPS when outdoors. The default mission is a single operator watching a video feed and steering the aircraft to look at something.<br>
**Operator** — Single operator via radio link. Optional supervised autonomy for position hold and return-to-home. The operator does not need to be a pilot; the flight controller handles stabilisation.<br>
**Reusability** — Repeatable build from off-the-shelf components. Production candidate.

---

## Spec

**Physical** — Target 180–220 g all-up weight without battery. 122 mm diagonal motor spacing. 2.5 mm T700 plain weave carbon fiber bottom plate, 1.5 mm top plate. Frame weight 27 g. Total frame dimensions 122 × 105 × 33 mm. The frame is the single largest structural contributor to AUW; every other component is chosen to fit inside it.<br>

**Kinematic** — 4 rotors, quadcopter X configuration. Fixed-pitch propellers. 2.5-inch props, 2-inch pitch, three-blade. 64 mm prop disc diameter. 5.5 mm center thickness. 10.6 mm maximum prop width. 1.5 mm T-mount. 1.0 g per prop.<br>

**Dynamic** — Thrust-to-weight ratio 2:1 minimum at hover. Target 15–20 min hover endurance with 3S 850 mAh LiPo. Estimated hover current draw 4–5 A total. Each motor produces approximately 101 g of thrust at 50% throttle at 16.79 V, drawing 1.49 A for 25.02 W, with an efficiency of 4.04 g/W. At 75% throttle, thrust rises to 188.96 g, current to 3.45 A, power to 57.86 W, and efficiency falls to 3.27 g/W. The peak thrust per motor at 100% throttle is 294.98 g at 16.73 V, drawing 6.38 A for 106.74 W, with an efficiency of 2.76 g/W. This data is critical for calculating hover throttle and expected flight time.<br>

**Power** — 3S LiPo, 850 mAh, 11.1 V nominal, 75C–150C discharge. XT30 connector. Battery weight 76–85 g. XT30 is rated for 30 A continuous and 45 A burst, which exceeds the drone's peak current draw of roughly 25.5 A (4 × 6.38 A). The connector choice is driven by weight and current capacity.<br>

**Thermal** — 10–35 °C operating. Passive cooling only. The flight controller and ESC generate heat under load; airflow from the propellers provides cooling. No active thermal management.<br>

**Environmental** — Calm indoor and outdoor. No rain, no dust. Not IP-rated. Optical flow requires >60 Lux illumination to function. Below that threshold, position hold without GPS degrades or fails.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $280–$350. Every part listed is chosen to fit the frame, meet the weight budget, and work with the selected firmware.<br>

**Structure** — 2.5 mm T700 plain weave carbon fiber bottom plate, 1.5 mm top plate. Unibody front-arm construction for drop resistance. Frame weight 27 g. T700 is a standard high-strength carbon fiber with a tensile strength of roughly 4.9 GPa and a density of 1.8 g/cm³. The unibody arms mean the front two arms are cut from the same piece of carbon as the bottom plate, eliminating a bolted joint that would be the first failure point in a crash. The 2.5 mm thickness is a deliberate compromise: thinner saves weight but flexes under thrust, thicker is stiffer but heavier. At this size, 2.5 mm is the standard for freestyle and cinewhoop builds.<br>

**Actuation** — 4× brushless motors, 1404 size, 3800 KV, 3S compatible. 9.34 g each including cables, 17.9 mm diameter, 16.6 mm height, 9N12P stator configuration, 1.5 mm shaft diameter, 24 AWG 150 mm leads, 195 mΩ internal resistance, 19 A peak current (60s), 304 W maximum power (60s). The 3800 KV rating is matched to 3S voltage and 2.5-inch props; higher KV would spin too fast for the prop load and waste energy as heat, lower KV would not produce enough thrust. The 9N12P configuration is a 12-slot stator with 9 poles, a standard high-torque-density layout for small multirotor motors.<br>

**Locomotion** — Aerial. 4 rotors. DShot motor protocol for low-latency control. DShot is a digital protocol that sends throttle commands as digital packets rather than PWM pulses, eliminating calibration drift and allowing bidirectional communication for RPM telemetry. DShot600 supports up to 32 kHz input rates, which is far above the flight controller's 1 kHz control loop. Bidirectional DShot (available on BLHeli_S with Bluejay firmware) sends RPM back to the autopilot without a separate telemetry wire, enabling better filtering.<br>

**Manipulation** — None. Payload is sensor only.<br>

**Power system** — 3S 850 mAh LiPo, 75C–150C discharge. XT30 connector. The 850 mAh capacity is a balance between flight time and weight; a larger battery adds flight time but also adds grams, which reduces the thrust margin and increases hover current. The 75C discharge rating means the battery can deliver 63.75 A continuously (850 mAh × 75C / 1000), far above the drone's peak draw of ~25.5 A. The XT30's 30 A continuous rating is sufficient. A 45 mm discharge wire and 45 mm balance wire keep the battery leads short to reduce resistive losses and weight.<br>

**Wiring** — 30 AWG signal wires, 20 AWG power leads. Motor wires soldered directly to ESC pads. Silicone insulation for heat resistance. The motor wires are enamelled magnet wire and must be tinned at 350–370 °C to burn off the enamel before soldering to the ESC. Power leads (battery to ESC) use 20 AWG wire, which handles the current with minimal voltage drop. All signal wires are 30 AWG, carrying only low-current logic signals. Leave 10 mm of slack in motor wires — too short pulls on the pads in a crash, too long creates a mess.<br>

**Custom parts** — Camera mount (3D printed TPU for vibration damping). GPS/RX tray (3D printed PA12 or PETG). Antenna mount (3D printed TPU). Optical flow mount (3D printed PA12). TPU is chosen for the camera mount because it absorbs vibration that would otherwise blur the video feed. PA12 is chosen for the GPS and optical flow mounts because it is stiffer and dimensionally stable, which matters for sensor alignment. All custom parts must be included in the weight budget.<br>

**Fasteners** — Titanium M2 screws for weight reduction. M2 nylon standoffs for electronics mounting. M3 bolts on 5-inch builds need 0.4–0.6 Nm torque; for M2 on this frame, use the manufacturer's recommendation and do not overtighten into carbon, which crushes easily. Titanium saves roughly 40% of the mass of steel screws. Nylon standoffs are used where electrical isolation is needed and where crash energy should be absorbed rather than transmitted.<br>

**Tools required** — Soldering iron (fine tip, 60/40 or lead-free), hex drivers (1.5 mm, 2 mm), wire cutters, multimeter, tweezers, heat gun for shrink tube. The soldering iron should melt 63/37 solder on a motor pad within 2 seconds of contact at 350 °C. A 3.2 mm chisel tip is recommended for motor wire to ESC pad joints. A multimeter is mandatory for checking continuity and polarity before first power-up.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| 2.5" carbon fiber frame (Flywoo Firefly 25 MINI or equivalent) | 1 | Flywoo / Rotorama | ~€32 | Frame/2.5-inch |
| 1404 3800KV brushless motors (T-Motor F1404 or equivalent) | 4 | T-Motor / iFlight | ~$60 | Actuators/BLDC |
| 4-in-1 ESC, 20A, 2–4S, BLHeli_S or AM32 | 1 | Various (Flywoo GOKU, Turnigy MultiStar) | ~$25 | Actuators/ESC |
| Flight controller, 20×20, H743, dual BMI088, PX4/ArduPilot (MicoAir NxtPX4v2) | 1 | MicoAir | ~€61 | Compute/FC |
| ExpressLRS 2.4 GHz nano receiver (RadioMaster XR2 Nano or equivalent) | 1 | RadioMaster / iFlight | ~$13 | Comms/ELRS |
| BN-220 GPS module | 1 | Beitian | ~$10 | Sensors/GPS |
| Optical flow + lidar sensor (Matek 3901-L0X) | 1 | Matek | ~€33 | Sensors/OpticalFlow |
| FPV camera (Caddx Ant Nano or Runcam Nano) | 1 | Caddx / Runcam | ~$20 | Sensors/Camera |
| VTX (video transmitter, 5.8 GHz, 25–400 mW) | 1 | Various | ~$15 | Comms/VTX |
| Gemfan 2520-3 propellers | 4 | Gemfan | ~$1/pair | Locomotion/Props |
| 3S 850 mAh LiPo battery | 1–2 | Tattu | ~$18 each | Power/Battery |
| Antenna (2.4 GHz for ELRS, 5.8 GHz for VTX) | 2 | Various | ~$8 | Comms/Antenna |
| Misc (wires, screws, connectors, heat shrink) | — | — | ~$20 | — |

---

## Systems

**Manifest** — See detailed manifest below.<br>

**Firmware** — ArduPilot 4.5+ or PX4 1.15+ on STM32H743. BLHeli_S or AM32 on ESC. ArduPilot has been the primary development target for this build because of its extensive parameter set and its support for the Matek 3901-L0X optical flow sensor via the MSP protocol. PX4 is supported on the same hardware and is an alternative if the operator prefers the PX4 ecosystem. The ESC firmware choice determines whether bidirectional DShot is available; BLHeli_S with Bluejay firmware enables it, while stock BLHeli_S does not.<br>

**Middleware** — MAVLink over UART. Optional ROS 2 via companion computer (e.g., Raspberry Pi Zero 2W). MAVLink is the universal language of drone telemetry and command. It carries attitude, position, battery state, GPS status, and flight mode at a configurable rate. If a companion computer is added later, MAVROS bridges MAVLink into ROS 2, allowing the drone to participate in a larger robotics stack. For the initial build, MAVLink alone is sufficient; the operator uses a ground station like Mission Planner or QGroundControl to see telemetry and issue commands.<br>

**Perception** — FPV camera for operator view. Optical flow (PMW3901) + lidar (VL53L0X) for position hold without GPS. Working range 8–200 cm, FOV 42° for optical flow and 27° for lidar, minimum illumination >60 Lux, 40 mA current draw, 4.5–5.5 V input. The PMW3901 optical flow sensor works like an optical mouse, tracking movement of the ground beneath the drone. The VL53L0X lidar measures altitude up to 2 m. Together they enable FlowHold mode: the drone holds position by compensating for detected motion, without GPS. This is the critical sensor for indoor operation. The sensor must be mounted on the underside with the lens pointing down, and the small arrow on the board must point forward.<br>

**Control** — ArduPilot/PX4 stabilisation loop at 1 kHz. Motor control via DShot. PID tuning for rate and attitude control. The flight controller runs an inner loop that stabilises the aircraft's attitude (roll, pitch, yaw) at 1 kHz, and an outer loop that handles position and altitude. The inner loop is what makes the drone flyable; without it, the operator would be balancing four independent motors by hand. The default PID gains are tuned for larger aircraft and will not work on a 2.5-inch quad. Rate P and I parameters must be reduced from the default of 0.135, and vertical acceleration controller gains must be lowered from default. The tuning process is covered in the Trials section.<br>

**Planning** — Waypoint navigation via GPS. FlowHold mode for GPS-denied position hold using optical flow. In outdoor flight, the operator can set waypoints on a map in the ground station and the drone will fly the mission autonomously. Indoors, FlowHold mode uses the optical flow sensor to hold position when the operator centres the sticks. The drone will drift slowly if the lighting is poor or the ground texture is featureless, because optical flow needs contrast to track motion.<br>

**Learning** — None initially. Data collection for future policy training possible. The flight controller logs flight data to an SD card, including attitude, position, motor outputs, and sensor readings. This data could later be used to train a policy that reproduces hover or position-hold behaviour, but the initial build does not include any learning capability.<br>

**Teleoperation** — RC transmitter via ExpressLRS 2.4 GHz. Optional ground station via MAVLink. ExpressLRS is an open-source radio link that supports packet rates from 25 Hz for maximum range up to 1000 Hz for racing. At 500 Hz, stick latency is 6.5 ms, which is competitive with a wired connection for all practical purposes. The operator holds a transmitter, moves the sticks, and the receiver on the drone translates those movements into control inputs for the flight controller. The link also carries telemetry back to the transmitter, so the operator can see battery voltage, GPS lock, and signal quality on the radio screen.<br>

**Safety** — Failsafe return-to-home, low battery failsafe, geofence, motor stop on disarm. Arming checks. The flight controller is configured to return the drone to its takeoff point if the radio link is lost, if the battery drops below a threshold, or if the drone leaves a defined geofence. Motor stop on disarm means the props do not spin when the drone is disarmed on the ground. Arming checks prevent the drone from taking off if the sensors are not calibrated or if the GPS fix is insufficient.<br>

**Logging** — SD card on flight controller. MAVLink telemetry to ground station. The SD card records every parameter and sensor reading at high rate for post-flight analysis. This is essential for tuning and for diagnosing crashes.<br>

**Networking** — 2.4 GHz control link (ELRS), 5.8 GHz video link (analog or HD). The control link and video link are separate radio systems on different frequencies. The control link carries commands to the drone and telemetry back. The video link carries the camera feed from the drone to the operator's goggles or screen. Running them on separate bands prevents interference.<br>

**Config files** — ArduPilot parameter file, PID tune, optical flow calibration. The parameter file is the complete configuration of the flight controller. It should be saved and version-controlled.<br>

**Launch files** — N/A (firmware-based).<br>

**Dependencies** — Mission Planner or QGroundControl for configuration. Both are free ground station applications that run on a laptop and connect to the flight controller via USB or telemetry radio.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ArduPilot | 4.5+ | ardupilot.org | Middleware/Autopilot |
| PX4 | 1.15+ | px4.io | Middleware/Autopilot |
| BLHeli_S / AM32 | Latest | github | Firmware/ESC |
| ExpressLRS | 3.x | expresslrs.org | Comms/Radio |
| Mission Planner | Latest | ardupilot.org | GCS |
| QGroundControl | Latest | qgroundcontrol.com | GCS |
| MAVROS (optional) | Latest | ROS 2 | Middleware/MAVROS |

---

## Interface

**Emits** — MAVLink telemetry: attitude, position, battery, GPS, flight mode. Video feed via VTX. Telemetry is broadcast at a configurable rate (typically 1–10 Hz for most fields, faster for attitude). The video feed is continuous at the camera's frame rate.<br>

**Accepts** — RC commands via ELRS. MAVLink commands via ground station. RC commands are the primary control path; MAVLink commands are used for setup, calibration, and autonomous missions.<br>

**Serves** — Arming, calibration, parameter access via MAVLink. The ground station can request and set any parameter, run calibration routines, and arm or disarm the drone.<br>

**Executes** — Waypoint missions, RTL, loiter, guided mode via MAVLink. Guided mode allows the operator to click a point on the ground station map and have the drone fly there autonomously.<br>

**Extensions** — Custom MAVLink messages if companion computer added.<br>

**Frame conventions** — NED (North-East-Down) for navigation. FRD (Forward-Right-Down) for body. NED is the standard aerospace convention: X points north, Y points east, Z points down. FRD is the body-frame equivalent: X points forward, Y points right, Z points down. The flight controller uses these to interpret sensor data and motor commands.<br>

**Units** — SI. Meters, meters/second, radians for attitude.

---

## Model

**URDF / Xacro** — Optional. Generated from frame dimensions.<br>

**SDF** — Used for Gazebo simulation if needed.<br>

**Calibration** — Accelerometer, gyroscope, compass, level horizon. ESC calibration. Optical flow calibration. Lidar range calibration. Accelerometer calibration is mandatory before first flight; it tells the flight controller which way is down. Gyroscope calibration removes bias. Compass calibration is only needed if a compass is fitted; the NxtPX4v2 has no onboard compass and relies on an external one in the GPS module if fitted. Optical flow calibration sets the FLOW_FXSCALER and FLOW_FYSCALER parameters, which scale the raw sensor output to real motion.<br>

**Dynamics** — Thrust curve from motor/prop combo. Frame inertia estimated from CAD. PID tune for rate and attitude control. The thrust curve is the relationship between throttle command and actual thrust, measured on a thrust stand or taken from the motor manufacturer's data. Frame inertia is estimated from the mass distribution of the components. These two pieces of data feed the PID tuning process.<br>

**Sensor transforms** — Camera mount angle. GPS mount position. Optical flow mount position (downward-facing, lens pointing down, arrow pointing forward). The flight controller needs to know where each sensor is mounted so it can correctly interpret the data. The optical flow sensor's arrow must point forward, or the drone will fly sideways when trying to hold position.<br>

**Collision geometry** — Simple box approximations for simulation.<br>

**Visual geometry** — Frame mesh, motor meshes, prop meshes.

---

## Trials

**Bench** — Motor spin direction, ESC calibration, receiver binding, GPS fix, optical flow test. Pass/fail, measured values, date. Motor spin direction is the first test: if any motor spins the wrong way, the drone will flip on takeoff. ESC calibration ensures all four ESCs interpret throttle commands identically. Receiver binding confirms the ELRS link works. GPS fix confirms the module can see enough satellites. Optical flow test confirms the sensor reports motion when the board is moved.<br>

**Integration** — Hover test, position hold test, RTL test, failsafe test. Pass/fail, measured values, date. The hover test is the first flight: lift off to 1 m and hold. Position hold test: centre the sticks and confirm the drone stays within a 1 m box. RTL test: trigger return-to-home and confirm the drone returns. Failsafe test: turn off the transmitter and confirm the drone returns home.<br>

**Field** — Endurance test, range test, video link test. Pass/fail, measured values, date. Endurance test: hover until the battery hits the low-voltage threshold and record the time. Range test: fly out until the control link drops and record the distance. Video link test: fly out until the video degrades and record the distance.<br>

**Endurance** — Continuous hover time recorded. Battery degradation observed. The theoretical hover time can be calculated from battery capacity and current draw: `flight time (min) = (battery capacity (mAh) × discharge factor / average current (A)) × 60`. For an 850 mAh battery, 80% usable capacity, and 4.5 A average hover current, that is approximately 9 minutes. Real-world flight time will be lower due to voltage sag, wind, and manoeuvring. The actual measured value is what goes in the log.<br>

**Environmental** — Tested temperature range, wind tolerance. The drone is tested indoors and in calm outdoor conditions. Wind tolerance is limited by the thrust margin; a 2:1 thrust-to-weight ratio allows the drone to fight moderate wind but not gusts.<br>

**Known limitations** — Not for rain, high wind, or GPS-denied environments beyond optical flow range. Optical flow fails on featureless surfaces (smooth tile, uniform carpet) and in low light (<60 Lux). GPS fails indoors.

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

**Next steps** — Finalise BOM, order components, begin assembly. The first build will reveal which parts need adjustment. The most likely issues are motor wire length, frame fit, and PID tuning. All three are solvable with the information in this document.
