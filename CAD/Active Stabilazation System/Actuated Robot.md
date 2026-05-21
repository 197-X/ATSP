# Actuated Robot
### The platform's main mechanism is composed of four distinguishable mechanical arms on each side of the chassis and two load-transferring beds that can translate on the x- and y-axes respectively.

## 1. Base load-Transferring Beds
The base beds consist of two layers. The first layer traverses the y-axis using a high-torque lead screw and two dovetail rails to guide the load. The second layer operates similarly, traversing the x-axis.
- They alleviate the arms from complex kinematic calculations and reduce potential points of failure.
- The female dovetail attachments are approximately one-third the length of the male dovetails, optimizing pressure dispersion and minimizing bending forces.

## 2. Actuated Arms
Four arms are positioned around the chassis, connecting directly to the landing pad to enable angled tilt and minor rotational yaw adjustment. Each arm is driven by two joints: the "Base joint," which connects directly to the load bed, and the "Elbow joint," which links the two trusses connecting the chassis to the pad. A constant-velocity (CV) joint at the end effector provides three-axis rotation.
- They require less computational power than a Stewart platform, resulting in faster response times.
- The cross-pattern configuration provides the arms with exceptional flexibility through their respective drive beds, preventing the landing pad from colliding with any obstacles.

## 3. IMU Equipment and Components
The Inertial Measurement Unit (IMU) equipment and components used for the robot include the following:
- 9-DOF IMU Sensor: Provides three-axis readings for acceleration, angular velocity, and magnetic fields to ensure accurate self-calibration.
- Barometer: Compensates for altitude changes and detects when the platform has been deployed and is stationary, initiating autonomous calibration and rigging.
- I2C Multiplexer / SPI Communication Protocol: An I2C multiplexer manages all data channels from the arms using dedicated IDs (for the prototype), while the SPI protocol handles rapid, autonomous self-leveling to maintain balance. (finalized prototype to commercial product)
- High-Clock-Speed MCU: Reads data and executes necessary states at high speeds to prevent the platform from losing balance.
- Sensor Fusion Firmware: Combines accelerometer and gyroscope data to filter out high-frequency vibrations and eliminate joint-angle drift errors.
