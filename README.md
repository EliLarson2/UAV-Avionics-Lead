# UAV Avionics and Systems Integration

This repository documents some of my experience working on autonomous UAV systems at the University of Nebraska-Lincoln.

I spent most of my time working on avionics and system integration. That meant working with flight controllers, sensors, RF communications, motor controllers, onboard computing, payload electronics, and the electrical interfaces connecting those systems together.

The biggest thing UAV taught me was that getting an individual component working is only part of the problem. Everything eventually has to work together on the aircraft.

A sensor can work perfectly on the bench and still cause problems once installed. A flight-controller fault can initially look like a software problem and turn out to be electrical. A radio can work independently and behave differently once integrated with the rest of the aircraft.

Learning how to troubleshoot across those boundaries was probably the part of UAV I enjoyed most.

> **Note:** This repository only contains material I am comfortable sharing publicly. Team-owned source code, detailed schematics, CAD files, configuration files, and other non-public technical material are intentionally excluded.

---

## What I Worked On

My UAV experience included:

- Flight-controller integration
- GPS and IMU sensors
- Range and proximity sensors
- RF communications and telemetry
- Motor-controller and propulsion interfaces
- NVIDIA Jetson Orin onboard computing
- Hardware assembly and rework
- Electrical troubleshooting
- Hardware bring-up
- Hardware-in-the-loop testing
- Ground-control systems
- Flight testing
- Cross-disciplinary system integration

I eventually served as Avionics Lead and coordinated work across avionics, embedded software, propulsion, payload, flight controls, autonomous navigation, and airframe teams.

---

## System-Level Avionics

At a high level, the aircraft combined sensing, flight control, communications, propulsion, payload electronics, and onboard computing.

```text
       GPS / IMU / Range Sensors
                 |
                 v
          Flight Controller
         /       |        \
        /        |         \
  Telemetry   Propulsion   Payload
        \        |         /
         \       |        /
          Onboard Computing
             Jetson Orin
                 |
                 v
          Complete Aircraft
```

This is intentionally a generalized representation rather than an actual aircraft wiring diagram.

What interested me most was understanding the interfaces between these systems: where power came from, what information moved between devices, how the devices communicated, and how a failure in one subsystem could show up somewhere else.

---

## Hands-On Avionics Work

Images/avionics_assembly.jpg

*Hands-on electronics assembly and rework during UAV development.*

A lot of avionics work came down to basic electrical-engineering fundamentals: making good connections, checking solder joints, reading documentation, confirming power, inspecting assemblies, and physically measuring signals.

That experience reinforced something I still use when debugging hardware today: before assuming a complicated failure, verify the fundamentals.

I learned to start with questions like:

- Is the device actually receiving the correct voltage?
- Is the expected ground reference present?
- Is the connector pinned correctly?
- Is the communication signal physically present?
- Is there visible damage or an assembly problem?
- What changed between the working bench configuration and the integrated aircraft?

Those questions sound simple, but they eliminated a lot of possible failure modes before moving into more complicated troubleshooting.

---

## Board Inspection and Debugging

Images/pcb_inspection.jpg

*Inspecting UAV electronics during bench-level troubleshooting.*

Visual inspection and bench testing were useful for finding problems before hardware made its way into the complete aircraft.

Depending on the problem, that meant checking component placement, soldering, connectors, wiring, continuity, power, or communication signals.

One of the more useful things I learned was not to assume that the place where a failure becomes visible is necessarily where the failure originates.

My general troubleshooting process became:

1. Understand what the system is supposed to be doing.
2. Measure what it is actually doing.
3. Narrow the problem to a subsystem or interface.
4. Form a hypothesis based on the measurements.
5. Test that hypothesis.
6. Verify the correction.
7. Retest it as part of the complete system.

That same process eventually carried into custom PCB bring-up and embedded-hardware projects.

---

## RF, Power, and Payload Integration

Images/rf_payload_integration.jpg

*Bench integration of communications hardware, power, wiring, and payload electronics.*

UAV avionics involved much more than the flight controller.

Communication hardware, cameras, sensors, batteries, flight electronics, payload systems, and onboard computing all introduced different electrical and physical requirements.

That forced me to think beyond whether an individual component worked.

I also had to consider practical questions like:

- Where does this device receive power?
- What voltage and current does it require?
- How does it communicate with the rest of the aircraft?
- What other subsystem relies on its output?
- How will it physically mount inside the aircraft?
- Can we still access it once everything is assembled?
- How will we troubleshoot it if it stops working?

This was one of the experiences that pushed me toward system-level electrical engineering.

I enjoy understanding individual circuits and boards, but I also want to understand why the electronics exist and how they affect the complete machine.

---

## Flight Controller and Ground Systems

Images/ground_control.jpg

*Working with aircraft telemetry and ground-control software.*

The flight controller sat near the center of much of the avionics integration.

Sensors, telemetry, propulsion interfaces, and onboard systems interacted with it in different ways. That made troubleshooting interesting because the distinction between a hardware issue and a configuration or software issue was not always obvious.

A sensor could have valid power but incorrect configuration.

A communication interface could be electrically functional while using incorrect settings.

A flight-controller fault could originate somewhere else in the electrical system.

Working with the flight-control and ground-station environment helped me become more comfortable troubleshooting across the hardware/software boundary instead of treating the two as completely separate systems.

---

## Integrating Everything Into the Aircraft

Images/aircraft_integration.jpg

*Physical integration work on a multirotor UAV.*

This was probably the biggest difference between UAV and a normal electronics assignment.

Eventually the electronics had to fit and operate inside a real aircraft.

Electrical decisions interacted with:

- Propulsion
- Payload requirements
- Mechanical mounting
- Communication systems
- Flight-control requirements
- Onboard computing
- Weight
- Available space
- Connector accessibility
- Power distribution
- Maintainability

That meant the technically best solution for one subsystem was not always the best solution for the aircraft.

Sometimes a design had to change because it made installation harder, created problems for another team, added unnecessary complexity, or increased integration risk.

That experience gave me a much better appreciation for engineering tradeoffs.

---

## Hardware-in-the-Loop and System Testing

Another important part of UAV development was learning that testing should happen at several levels.

I worked with hardware-in-the-loop testing and system validation before relying on the complete aircraft.

A component working independently was not enough. The interfaces between components had to work too.

I started thinking about testing in stages:

1. Verify the component or device.
2. Verify power and electrical interfaces.
3. Verify communication with the flight controller or onboard computer.
4. Verify the subsystem.
5. Run hardware-in-the-loop or controlled system tests.
6. Ground-test the integrated aircraft.
7. Validate the complete aircraft during flight testing.

Finding a problem earlier in that process was usually much easier than discovering it for the first time during a flight test.

---

## Flight Testing

Images/flight_testing.jpg

*Taking avionics work out of the lab and validating the complete aircraft.*

Flight testing was where the entire system had to prove itself.

At that point, the question was no longer whether an individual board, sensor, or radio worked.

The question became whether the aircraft worked.

A problem during flight testing could potentially come from:

- Power
- Electronics
- Sensor behavior
- Flight-controller configuration
- RF communications
- Propulsion
- Embedded software
- Autonomous-navigation software
- Mechanical integration

Being able to work through those possibilities systematically was one of the most valuable things I learned from UAV.

---

## Working Across Disciplines

One of the things I liked most about avionics was that it naturally crossed into other engineering disciplines.

An avionics decision could affect propulsion.

A mechanical change could affect sensor placement.

A software requirement could affect which interfaces the hardware needed.

A payload requirement could affect power, communications, mounting, and onboard computing at the same time.

That meant communication between teams was just as important as understanding the electronics.

---

## Leading the Avionics Team

I eventually served as Avionics Lead and worked with a team of roughly 20 members.

That experience changed how I thought about engineering leadership.

I did not need to be the person who knew the most about every sensor, piece of firmware, RF link, motor controller, or autonomous-navigation system.

I needed to understand the interfaces well enough to help the different parts of the team work together.

When technical disagreements came up, I tried to bring the discussion back to actual engineering constraints:

- Does the approach meet the requirements?
- Is it reliable?
- How difficult is it to integrate?
- What does it cost in time?
- What does it cost financially?
- Does it create problems for another subsystem?
- Can it be tested and debugged?
- Does it decrease or increase overall project risk?

That became increasingly important as competitions and deadlines approached.

---

## What UAV Changed for Me

UAV was probably the experience that made me realize I enjoy system-level electronics.

I still like board-level hardware, circuits, embedded interfaces, and debugging individual components.

But I get the most interested when those things become part of a larger physical machine.

UAV exposed me to the entire path between a sensor collecting information and an aircraft physically responding to that information.

It also showed me why understanding the interfaces between electrical hardware, embedded software, RF communications, propulsion, sensors, and mechanical systems matters.

That is the kind of engineering I want to continue doing professionally.

---

## Areas of Experience

### Avionics

- Flight-controller integration
- GPS and IMU sensors
- Range sensing
- Embedded electronics
- Motor-controller interfaces

### Communications

- RF links
- Telemetry
- Ground-control interfaces
- Communication troubleshooting

### Computing

- NVIDIA Jetson Orin
- Autonomous-navigation hardware
- Hardware/software interfaces

### Testing

- Bench testing
- Hardware bring-up
- Hardware-in-the-loop testing
- System validation
- Ground testing
- Flight testing
- Fault isolation

### Systems Engineering

- Interface coordination
- Requirements discussions
- Multidisciplinary design decisions
- Integration troubleshooting
- Technical tradeoffs

### Leadership

- Avionics team leadership
- Cross-disciplinary coordination
- Technical decision-making
- Competition preparation

---

## Public Material Only

The UAV program was a team effort involving electrical hardware, software, mechanical design, flight controls, and autonomous systems.

I intentionally do not publish team-owned source code, detailed electrical schematics, PCB design files, internal wiring diagrams, CAD files, aircraft configuration files, or technical documentation that I cannot clearly treat as public material.

This repository is meant to document my experience with **avionics integration, testing, debugging, and system-level engineering**, not reproduce the team's aircraft design.

---

## Why This Project Is in My Portfolio

My other projects show individual technical areas:

- Custom PCB design and bring-up
- FPGA/VHDL development
- Digital signal processing
- Mixed-signal embedded systems
- Autonomous mobile robotics

UAV is different.

UAV is where I learned what happens when electronics, communications, software, sensors, actuators, and mechanical systems all have to work together inside a real machine.

That systems-level experience is the part I want to keep building on.
