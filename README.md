# Autonomous-Post-Disaster-Patrolling-and-Survivor-Detection-Rover
4WD Arduino Uno R3 robot car with L293D shield tracks paths using servo-mounted ultrasonic radar. Maps surroundings over 180°, dodging barriers. Built-in MQ gas and PIR motion sensors detect environmental hazards instantly, flashing an LED and streaming real-time diagnostic telemetry to a 9600-baud serial monitor. Powered cleanly by 18650 cells.

2. Mission Objective
The primary mission is to engineer an autonomous vehicle capable of safely traversing unknown indoor terrain without human intervention. The control system must continuously optimize its forward path based on real-time acoustic scanning boundaries, while simultaneously executing immediate threat mitigation routines (such as halting or emitting localized visual alerts) upon detecting hazardous gas or moving physical intrusions.

3. Core Features
•	Smart Radar Navigation: Utilizes an SG90 micro-servo motor to physically sweep an HC-SR04 ultrasonic distance sensor across a 180° tracking frame. This allows the car to evaluate alternative side openings when its primary path is obstructed.
•	Dual-Hazard Telemetry: Integrated with a specialized MQ-series gas sensor and an infrared PIR motion sensor to intercept airborne and kinetic threats in its workspace.
•	Integrated Power Architecture: Employs a single 18650 high-drain battery pack configured with a unified power-bridging shunt to simultaneously run heavy motor gears and sensitive microcontrollers without voltage drops.
•	Real-Time Data Analytics: Includes diagnostic serial pipeline reporting at 9600 baud, allowing operators to monitor target distances and environmental sensor flags in real time via an attached console terminal.

4. Setup Instructions
Hardware Assembly
1.	Chassis Setup: Mount your four DC yellow gearboxes to the structural chassis plate and tighten the structural mounts securely.
2.	Microcontroller Stack: Align the pins underneath the L293D Motor Shield carefully with the female headers of the Arduino Uno R3 and press them together until they are flush.
3.	Radar Rigging: Secure the base of your SG90 Servo to the front bumper of your chassis. Use adhesive tape or a bracket to mount the HC-SR04 Ultrasonic Sensor directly onto the servo horn.
4.	Breadboard Power Hub: Connect the 5V and GND output header terminals from the top of the L293D shield to the positive (+) and negative (-) rails of an adjacent breadboard to create a shared power grid.

Wiring Guide
•	Actuators: Connect the Left Front, Left Rear, Right Front, and Right Rear motor leads to the shield's screw terminals M1, M2, M3, and M4, respectively. Plug the servo cable directly into the SERVO_1 header pin interface.
•	Sensors: Plug the Ultrasonic, PIR, and Gas modules into the breadboard center blocks. Map their VCC/GND terminals to the main breadboard rails, then route their digital signal pins to the shield’s analog breakouts: Trig → A0, Echo → A1, PIR Out → A2, and Gas Out → A3.
•	System Alert: Connect a red LED (in series with a 220Ω resistor) across the breadboard grid, routing its positive input terminal back to shield pin A4 and its ground wire to the negative rail.
•	Power Switch Input: Connect the black wire of your 18650 battery holder to the GND terminal of the shield’s EXT_PWR block. Splice a toggle switch inline with the red battery wire, connecting its output lead to the +M terminal. Ensure the shield's yellow power jumper cap is securely ON.

Software Configuration
1.	Open the official Arduino IDE application on your computer.
2.	Navigate to Sketch → Include Library → Manage Libraries....
3.	Search for the Adafruit Motor Shield library and install Version 1.x.x (V1). Do not install Version 2.
4.	Copy the complete master code into your editor workspace, compile it to check for syntax bugs, and upload it via a USB cable.
5.	Unplug the USB cable, turn on your battery power toggle switch, open the Serial Monitor (9600 Baud), and place the car on an open floor to test its autonomous routines.
