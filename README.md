# ATSP
Adaptive Terrain Stabilization Platform (ATSP) is a deployable terrain-stabilization system designed to provide a stable operational surface for remote-operated and autonomous systems in uneven or unstable environments. [Developed from absolute scratch without previous knowledge (CAD, Architecture, and Repository) in a focused 23-day sprint.

## Overview
### 1. Core Problems
---
### 2. Goals
---
### 3. Repository Structure
#### 3.1. About Progess
#### 3.2. About Data
---
### 4. Current MVP Scope
---
### 5. System Architecture
#### 5.1. Structural Frame
#### 5.2 Deployment System
#### 5.3 Sensor & Control System
---
### 6. Materials and Manufacturing
#### 6.1. Candidate Materials
#### 6.2. Material Selection Logic
#### 6.3. Manufacturing Concepts
#### 6.4. Project Evaluated Costs
---
### 7. Market
#### 7.1 Market Scope
#### 7.2 Market Competition
#### 7.3 Strategic Positioning
---

## 1. Core Problems
- ### 1.1 Ground Compliance Failure
Most autonomous systems assume a rigid, level ground plane. On non-homogeneous surfaces (mud, loose scree), point-loading causes differential sinkage, leading to tip-over or sensor misalignment.
- ### 1.2 Static vs. Dynamic Load Instability
Current stabilization solutions are often too slow to react to shifting loads (e.g. a robotic arm extending or a UAV landing), resulting in harmonic oscillation or mechanical fatigue at the joints.
- ### 1.3 Deployment Latency
Manual leveling is time-expensive. The lack of a self-correcting mechanical base prevents true "drop-and-forget" autonomous deployment in remote sectors.
- ### 1.4 Infrastructure Absence & Surface Unpredictability
Remote environments lack prepared landing pads or stabilized surfaces. This forces systems to operate on unprepared topography, where localized micro-obstructions and unpredictable slopes exceed the onboard suspension limits of most mobile robotics.
- ### 1.5 Asymmetric Structural Fatigue
Operating on uneven terrain creates unbalanced vector loading across a system's chassis. This leads to cyclic stress and vibration amplification at specific joints, causing accelerated mechanical wear and reducing the Mean Time Between Failure (MTBF) for the hosted equipment.

## 2. Project Goals
- ### 2.1 Autonomous Plane Stabilization
Achieve a true horizontal operational surface (±0.5°) across multi-axial slopes. The system must utilize closed-loop feedback to compensate for terrain irregularities without manual intervention.
- ### 2.2 Dynamic Load Mitigation
Minimize structural resonance and oscillation during payload operation. The platform must maintain equilibrium during active weight shifts, such as robotic arm articulation or high-impulse UAV landings.
- ### 2.3 Rapid Field Deployment
Reduce "Time-to-Level" to under 0.5 seconds. The mechanical architecture must prioritize a high strength-to-weight ratio to allow for deployment via drone or person-portable kits.
- ### 2.4 Structural Longevity & Load Distribution
Implement an intelligent footprint design that distributes localized pressure evenly. The goal is to prevent sinkage in soft media and eliminate the asymmetric stress concentrations that lead to premature joint failure.
- ### 2.5 Hardware Agnostic Interface
Develop a standardized mounting system that allows the ATSP to act as a universal base for various sensors, communication arrays, or robotic units, regardless of their specific center-of-gravity profiles.

## 3. Repository Structure
- ### 3.1. About Progess
This repository documents the ongoing research, development, and iteration process of the ATSP project. All major system revisions, mechanical concepts, calculations, prototype developments, and design changes are organized throughout the repository’s sub-categories. Each subsystem contains its own development history, including experimental concepts, failures, revisions, and engineering considerations explored during development. The project is actively iterated upon, with the repository serving as a living technical archive for the platform’s progression.
- ### 3.2. About Data
Project data, calculations, testing results, material evaluations, and engineering notes are distributed across the repository’s dedicated subsystem categories and supporting documentation.

As the project evolves, documentation and datasets will continuously change to reflect:
- new design iterations
- revised engineering assumptions
- prototype validation results
- terrain interaction testing
- structural and mechanical evaluations

The purpose of this data structure is to maintain traceable engineering development and provide a clear representation of how the MVP performs under different operating and terrain conditions.

## 4. Current MVP scope
The Minimum Viable Product (MVP) must meet the following performance and operational requirements:
- Maneuverability: The platform must be capable of tilting its landing pad by at least 30 degrees in any direction.
- Payload Capacity: It must support a minimum payload equivalent to a human weight, up to a maximum of 75 times its own structural weight.
- Operational Lifespan: The design must sustain continuous field missions lasting from several days to multiple weeks without requiring maintenance, effectively decoupling the platform from immediate logistical infrastructure support and reducing secondary operational costs.

## 5. System Architecture
- ### 5.1 Structural Frame
The structural frame comprises the landing pad, the body, the exoskeleton, and the foundation, with each component playing a crucial role in the design.
- Landing Pad: The landing pad is made of three distinct layers: the platform, the arms, and the load-bearing base. This layout provides multi-axis translation and decouples the arms from heavy IMU components, which can instead be mounted in structurally rigid areas of the landing pad.
- Exoskeleton: The exoskeleton consists of an inner and an outer cylindrical frame that connects the legs to the base. It utilizes trusses between the frames to counteract the large forces exerted on the platform.
- Foundation: The foundation is separated from the exoskeleton because it features an autonomously deployed Miura-ori origami mechanism. This mechanism expands lightweight, durable, thin metal composite plates to adapt to versatile terrains, distributing the pressure across multiple contact points so the platform does not sink into the ground.
- ### 5.2 Deployment System
The deployment of the platform will be conducted via heavy-duty cargo transportation UAVs, with a singular UAV assigned per platform. The platform's exoskeleton will feature dedicated attachment points for the UAV coupling systems, ensuring that no internal mechanisms or components are damaged during transit or release. To account for terrain irregularities, fast-paced tactical situations, and potential in-flight UAV anomalies, the UAVs will be capable of safely dropping the platform from an altitude of at least 5 meters.
- ### 5.3 Sensor & Control System
The platform utilizes sensors capable of detecting 9 to 10 Degrees of Freedom (DOF). The control system relies on high-frequency data throughput, delivering commands to every actuator and control hardware component within microseconds. This rapid cycle time is critical to compensate for computational latency and to react to drastic, real-time positional changes of both the platform and its cargo.

## 6. Materials and Manufacturing
### 6.1 Candidate Materials
The materials under consideration for machined components include the following:
- 1. Aluminum 6061-T6: Selected for its excellent machinability, high strength-to-weight ratio, and cost-effectiveness.
- 2. Stainless Steel 303: Selected for its ease of fabrication, high structural strength, and surface hardness.
- 3. Aluminum 7075-T6: Evaluated for its exceptional strength-to-weight ratio and superior hardness compared to standard aluminum alloys, balancing performance with its higher cost.
- 4. 4140 Steel (Pre-hardened): Utilized for its high fatigue strength, toughness, and excellent wear resistance in heavy-load applications.

The materials under consideration for 3D-printed components include the following:
- 1. PETG: Offers robust mechanical properties and high affordability, making it ideal for mass prototyping and experimentation.
- 2. ASA: Features high UV resistance and excellent thermal stability, making it suitable for localized heat shielding at a cost comparable to PETG.
- 3. PET-CF: Provides high tensile strength and rigidity, serving as a functional, low-cost alternative to metal components during the prototyping phase.
- 4. 85A TPU: Exhibits exceptional impact and wear resistance, making it ideal for printing shock absorbers that must yield slightly without failing under high-stress conditions.

### 6.2 Material Selection Logic
The candidate materials were selected based on three core engineering criteria:
- 1. High Specific Stiffness: Materials must minimize overall structural weight while retaining the durability and rigidity required to withstand operational loads.
- 2. Corrosion Resistance: Components must resist environmental degradation and chemical corrosion under harsh, unpredictable field conditions.
- 3. Cost-Effectiveness: The material selection prioritizes affordability to support rapid prototyping and multiple design iterations within tight funding constraints.

### 6.3 Manufacturing Concepts
The manufacturing strategy utilizes a hybrid approach tailored to different stages of development and component scale:
- 1. Additive Manufacturing (3D Printing): Employed for rapid prototyping and swift design iterations of complex, non-load-bearing components.
- 2. CNC Machining: Utilized for high-precision, fast production of small, high-stress components requiring strict dimensional tolerances.
- 3. Molding Processes: Selected for the scalable production of large, complex geometric structures such as the main chassis body.

### 6.4. Project Evaluated Costs
The prototyping and manufacturing budget covers three distinct prototypes. To account for the first two versions being entirely 3D-printed, all raw material filament quantities have been doubled from the initial baseline. A 20% contingency buffer is applied across the entire baseline subtotal to mitigate hardware risks, failures, or re-prints.
- 1. Equipment: A X2D AMS Combo + Accesories (€900-€1000) / JBC CD-2QWLF Digitale Lötstation Edition+ + Accesories (~€700) [Total €1,700.00]
- 2. Materials: PETG 30kg * €13 (€390) / ASA 1kg * €25 (€25) / PET-CF 5kg * ~€90 (~€500) / 85A TPU 2kg * €48 (€96) / [Metal components will be off the shelf] [Total €2,022.00 / With 20% = €2,426.40]
- 3. Electronics: [To be researched] 
## 7. Market
### 7.1 Market Scope
The market scope for the product is global, targeting the mining, construction, military, and civilian sectors. It focuses on autonomous resupply operations in critical, high-risk environments requiring the rapid transportation of heavy payloads.
### 7.2 Market Competition
While agencies and private corporations are gradually researching and developing technologies in this sector, existing solutions are rarely pushed to the heavy-payload extremes required to capture high-value cargo markets. Key players and current technologies include:
- NASA: Developed and patented the Programmable Lead Screw Actuated Self-Leveling Platform (PLSASLP) to provide a load-bearing foundation for autonomous planetary surface robotics and early space infrastructure.
- STABLE AS: A maritime-focused company providing active stabilization platforms ranging from 2 to 4 Degrees of Freedom (DOF). Their systems compensate for up to 30 degrees of environmental roll and pitch, supporting payloads from 10 kg to approximately 250 kg.
- SANLAB Simulation: An industry leader in real-time robotics and motion platforms, producing active stabilization systems ranging from 2 to 6 DOF. Their specialized heavy-duty systems support up to 3 tons of cargo with a maximum tilt compensation of 15 degrees.
- HEISHA Technology: A provider of industrial drone-in-a-box infrastructure featuring an auto-stabilized drone landing platform. Their 2-DOF system automatically compensates for uneven terrain up to a 15-degree slope, supporting a 10 kg payload.
### 7.3 Market Positioning
The Adaptive Terrain Stabilization Platform (ATSP) fills a critical market gap by bridging high angular flexibility with immense load capacity. Operating between 3 and 4 Degrees of Freedom (DOF), the ATSP provides an industry-leading maximum tilt angle of 30 degrees while achieving a heavy cargo capacity of up to one ton. This dual capability allows the platform to play a crucial role in military logistics, remote mining operations, heavy construction setups, and civilian humanitarian aid.
