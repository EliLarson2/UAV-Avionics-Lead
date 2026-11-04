# UAV Avionics and Systems Integration

This repository documents some of my experience working on autonomous UAV systems at the University of Nebraska-Lincoln.

I spent most of my time on avionics and system integration. That meant working around flight controllers, sensors, RF communications, motor controllers, onboard computing, payload electronics, and the electrical interfaces that connected everything together.

The biggest thing UAV taught me was that getting an individual component working is only part of the problem. Everything eventually has to work together on the aircraft.

A sensor can work perfectly on the bench and still fail once it is installed. A flight-controller warning can look like a software problem and turn out to be electrical. A radio can work independently and then behave differently once it is packaged with the rest of the aircraft.

That system-level troubleshooting is what I enjoyed most.

> **Public-release note:** This repository only contains material I am comfortable sharing publicly. Team-owned source code, detailed schematics, CAD files, configuration files, and other non-public technical material are intentionally excluded.

---

## What I Worked On

My experience on the UAV team included:

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

As Avionics Lead, I also coordinated work across avionics, embedded software, propulsion, payload, flight controls, and airframe teams.

---

## System-Level Avionics

At a high level, the aircraft combined sensing, flight control, communications, propulsion, payload electronics, and onboard computing.

A simplified view of the architecture is:

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

This is intentionally a generalized architecture rather than an actual aircraft wiring diagram.

What interested me most was understanding the interfaces between these systems: where power came from, what information had to move between devices, how the devices communicated, and how a failure in one subsystem could appear somewhere else.

---

## Hands-On Avionics Work

Images/avionics_assembly.jpg

*Hands-on electronics assembly and rework during UAV development.*

A lot of avionics work came down to basic electrical-engineering fundamentals: making good connections, checking solder joints, reading documentation, confirming power, inspecting assemblies, and physically measuring signals.

That experience reinforced something I still use when debugging hardware today: before assuming a complicated failure, verify the fundamentals.

Is the device receiving the correct voltage? Is ground actually common? Is the connector pinned correctly? Is the signal physically present? Did something change between the bench configuration and the integrated aircraft?

The photo above corresponds to electronics assembly work at a soldering bench. 【1-c88066】



---

## Board Inspection and Debugging

Images/pcb_inspection.jpg

*Inspecting UAV electronics during bench-level troubleshooting.*

Visual inspection and bench testing were useful for finding problems before hardware made its way into the full aircraft.

Depending on the problem, that meant checking component placement, soldering, connectors, wiring, continuity, power, or communication signals.

The most useful lesson for me was learning not to assume that the place where a failure becomes visible is necessarily where the failure originates.

My general approach became:

1. Define what the hardware is supposed to be doing.
2. Measure what it is actually doing.
3. Isolate the affected subsystem.
4. Work backward through the interfaces.
5. Test the most likely explanation.
6. Verify the correction at the complete-system level.

That same process eventually carried into my PCB bring-up and embedded-hardware projects.

The photo above shows small UAV electronics being examined under a digital microscope. 【1-c88066】



---

## RF, Power, and Payload Integration

Images/rf_payload_integration.jpg

*Bench integration of UAV electronics, communications hardware, battery power, and payload equipment.*

UAV avionics gave me exposure to electronics that served very different purposes but still had to operate as one system.

Communication equipment, cameras, sensors, batteries, flight electronics, and payload hardware all introduced their own power, communication, and packaging requirements.

This forced me to think beyond whether a component worked individually.

I also had to think about practical questions such as:

- Where does the device receive power?
- What voltage and current does it require?
- How does it communicate with the rest of the aircraft?
- Does another subsystem depend on its output?
- Can the hardware still be accessed after installation?
- How will I troubleshoot it after everything is assembled?

That is one of the reasons I became interested in system-level electrical engineering rather than working only on isolated circuits.

The photo above shows UAV RF/electronics hardware, an antenna, camera, battery, and associated wiring during bench work. 【1-c88066】



---

## Flight Controller and Ground Systems

Images/ground_control.jpg

*Working with UAV telemetry and ground-control software.*

The flight controller sat near the center of most avionics integration work.

Sensors, telemetry, propulsion interfaces, and onboard systems all interacted with it differently. That made troubleshooting particularly interesting because the distinction between a hardware issue and a configuration or software issue was not always obvious.

A sensor could have valid power but incorrect configuration. A communication interface could be electrically functional but configured incorrectly. A reported flight-controller fault could originate somewhere else in the electrical system.

Working with the flight-control and ground-station environment helped me get better at thinking across those boundaries instead of treating hardware and software as completely separate systems.

The photo above shows ArduPilot-related ground-control software displaying aircraft telemetry and mapping information. 【1-c88066】



---

## Integrating Everything Into the Aircraft

Images/aircraft_integration.jpg

*Physical integration work on a multirotor UAV.*

This was probably the biggest difference between UAV and a normal electronics assignment.

The electronics eventually had to fit and operate inside a real aircraft.

Electrical decisions interacted with physical constraints, propulsion, payload requirements, communications, flight control, onboard computing, weight, space, and accessibility.

That meant the technically best solution for one subsystem was not always the best solution for the aircraft.

Sometimes a design decision had to be reconsidered because it made installation harder, created problems for another team, added unnecessary complexity, or increased integration risk.

That experience gave me a much better appreciation for engineering tradeoffs.

The photo above shows a large multirotor UAV during physical integration work. 【1-c88066】



---

## Hardware-in-the-Loop and System Testing

Another important part of the experience was learning that testing should happen at several levels.

I worked with hardware-in-the-loop testing and system validation before relying on the complete aircraft.

A component working independently was not enough. The interfaces between components had to be tested too.

I started thinking about testing as a progression:

- Verify the component or device.
- Verify the electrical interface.
- Verify communication with the flight controller or computer.
- Verify the subsystem.
- Verify the behavior in HIL or controlled testing.
- Verify the complete aircraft.

Finding a problem earlier in that process was usually much easier than discovering it for the first time during a flight test.

---

## Flight Testing

Images/flight_testing.jpg

*Taking avionics work out of the lab and validating the complete aircraft.*

Flight testing was where the entire system had to prove itself.

At that point, the question was no longer whether an individual board, sensor, or radio worked.

The question became whether the aircraft worked.

A problem during flight testing could potentially come from power, electronics, sensing, flight-controller configuration, RF communications, propulsion, software, or the physical aircraft itself.

Being able to work through those possibilities systematically was one of the most valuable things I learned from UAV.

The associated project photo shows an outdoor flight test with a UAV near a building. 【1-c88066】



---

## Leading the Avionics Team

I eventually served as Avionics Lead and worked with a team of roughly 20 members.

That experience changed how I thought about engineering leadership.

I did not need to be the person who knew the most about every sensor, piece of firmware, RF link, motor controller, or autonomous-navigation system.

I needed to understand the interfaces well enough to help the teams communicate and make good decisions together.

Technical disagreements became easier to resolve when the discussion came back to actual engineering constraints:

- Does the approach meet the requirements?
- Is it reliable?
- How difficult is it to integrate?
- What does it cost in time and money?
- Does it create problems for another subsystem?
- Can it be tested and debugged?
- Does it reduce or increase overall project risk?

That approach became especially important as competitions and deadlines got closer.

---

## What UAV Changed for Me

UAV was probably the experience that made me realize I enjoy **system-level electronics**.

I still enjoy board-level hardware, circuits, embedded interfaces, and debugging individual components.

But I get the most interested when those things are part of a larger physical machine.

UAV exposed me to the full chain between a sensor collecting information and an aircraft physically responding to that information. It also showed me why understanding the interfaces between electrical hardware, embedded software, communications, propulsion, and mechanical systems matters.

That is the direction I want to continue developing professionally.

---

## Areas of Experience

Through the UAV program I gained experience with:

**Avionics**
- Flight-controller integration
- GPS and IMU sensors
- Range sensors
- Motor-controller interfaces
- Embedded electronics

**Communications**
- RF links
- Telemetry
- Ground-control interfaces

**Computing**
- NVIDIA Jetson Orin
- Autonomous-navigation hardware
- Hardware/software integration

**Testing**
- Bench testing
- Hardware bring-up
- Hardware-in-the-loop testing
- System validation
- Flight testing
- Fault isolation

**Systems Engineering**
- Interface coordination
- Multidisciplinary design decisions
- Requirements discussions
- Integration troubleshooting
- Technical tradeoffs

**Leadership**
- Avionics team leadership
- Cross-disciplinary coordination
- Competition preparation
- Technical decision-making

---

## Public Material Only

The UAV program was a team effort involving electrical hardware, software, mechanical design, flight controls, and autonomous systems.

I intentionally do not publish team-owned source code, detailed schematics, CAD files, internal wiring diagrams, configuration files, or technical documents that I cannot clearly treat as public material.

This repository is meant to document my experience with **avionics integration, testing, debugging, and system-level engineering**, not reproduce the team's aircraft design.

---

## Why This Is in My Portfolio

My other projects show pieces of what I like doing:

- RP2040 shows board-level hardware design and bring-up.
- FPGA projects show digital design.
- DSP projects show signal processing.
- Mobile robotics shows sensing and autonomous control.
- MSP430 work shows embedded and mixed-signal systems.

UAV is where I learned what happens when those kinds of technologies have to work together inside a real machine.

That's the part of engineering I want to keep doing.
