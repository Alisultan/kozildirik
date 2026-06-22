Smart Running Glasses Project
README #1: Initial brainstorming & Research notes
Hello, hello guys. Your favorite Kazakh friend is here:)
Welcome to our project's first README file!!!
Currently, I have a lot of questions and caffeine in my brain and body, but I also have a desire, great teammates, and great friends.
WE GOT THIS.
The purpose of this document is to organize our ideas, identify key technical questions, assign research topics, and gradually build a roadmap for our Senior Design project.

TABLE OF CONTENTS
Page 2: Project Identity
1.	How should we call our glasses?
o	AMF
o	AFM
o	FAM
o	MAF
o	MFA
o	FMA
o	(I just took first initials of our last names)
o	Other ideas?

Page 3: System architecture & Hardware
2.	Which communication protocols should we use for each component?
o	UART
o	I2C
o	SPI
3.	Should we stick with ESP32?
4.	How and when are we going to design our own PCB?
5.	Should we add a smart ring or bracelet to offload some sensors and reduce weight?
6.	Is it possible to make the display appear/disappear using a button?
7.	What IMU should we use?
o	Prototype: MPU6050
o	Final Version: BNO085 / BNO086

Page 4: Team & Organization
8.	Who is going to be our fourth teammate?
9.	Safety considerations
10.	GitHub, communication, and project management
o	GitHub
o	Notion
o	Obsidian
o	Other suggestions?
11.	What programming language should we use?
o	Arduino C++
o	ESP-IDF
12.	What do we need to learn?

Page 5+: Detailed research sections














How should we call our glasses?
Right now, naming is not a priority. It was just a first question that came to my mind as we are already done with our project :)
The most important thing is building a working prototype.
We can revisit branding, naming, logos, and product identity once we have completed at least 50% of the project and have a clearer understanding of what makes our product unique.
Current ideas:
•	AMF
•	AFM
•	FAM
•	MAF
•	MFA
•	FMA















Communication Protocols & Initial Hardware Architecture
Prototype Architecture
GPS → UART
MAX30102 (Heart Rate Sensor) → I2C
BME280 (Temperature, Humidity, Pressure) → I2C
MPU6050 (IMU) → I2C
SSD1306 OLED Display → I2C
Button → GPIO
Battery Monitoring → ADC
Vibration Motor → PWM

Future Architecture
After the prototype is fully functional:
GPS → UART
BNO085/BNO086 (IMU) → SPI
Micro OLED HUD Display → SPI
Environmental Sensors → I2C
Heart Rate Sensor → I2C
Battery Management → I2C
(Sensors might get changed)

Why This Approach?
UART
Best suited for GPS modules because they continuously transmit location and speed information.
I2C
Perfect for sensors due to:
•	Fewer wires
•	Simpler PCB design
•	Easier prototyping
SPI
Ideal for:
•	High-speed displays
•	Advanced IMUs
•	Future performance improvements

For Summer 2026:
Use Arduino C++ and ESP32 DevKit.
Focus on building a complete working prototype before optimizing hardware.





3. Should we stick with ESP32?
Short answer: Yes.
For our prototype and likely for our Senior Design project, ESP32 is currently the best option because:
Advantages:
•	Not expensive
•	Huge community support
•	Built-in Wi-Fi and Bluetooth
•	Supports UART, I2C, SPI, PWM, ADC, and BLE
•	Large number of available libraries
•	Plenty of tutorials and documentation
•	Powerful enough for our current requirements
Potential future concerns:
•	Power consumption
•	Physical size of development boards
•	Limited processing power for advanced AR applications

Right now, we can use:
•	Summer Prototype → ESP32 DevKit V1
•	PCB Version → ESP32-WROOM-32
•	Future Commercial Version → Reevaluate after prototype validation
Decision:
Proceed with ESP32.

4. How and when are we going to design our own PCB?
Short answer:
Not now.
Our first goal is to build a fully functional prototype using off the shelf components.
Roadmap:
Phase 1 (Summer)
•	ESP32 DevKit
•	Breadboard
•	Sensors
•	Display
•	Working software
I’m going to spend 2-3 hours every day for our first prototype and will try to finish it by August 15th.
Phase 2 (Fall Semester)
•	Finalize hardware architecture
•	Select final sensors
•	Create schematic
•	Learn PCB design tools
Suggested software:
•	KiCad
•	EasyEDA
Honestly, no idea who will handle this part. We should discuss on the first week immediately how we will separate our work.
Phase 3 (Spring Semester)
•	Design PCB
•	Order PCB
•	Assemble PCB
•	Integrate into glasses frame
Important:
There is no reason to design a PCB before we know exactly:
•	Which sensors we are using
•	Which display we are using
•	Battery requirements
•	Mechanical layout
Decision:
Build first. PCB later.

5. Should we add a Smart Ring or Bracelet to offload some sensors and reduce weight?
Short answer:
Possibly, and this may actually improve the project.
Current concern:
Placing everything inside the glasses could create:
•	Excess weight
•	Battery limitations
•	Comfort issues
•	More complicated PCB design
Potential architecture:
Glasses:
•	Display
•	ESP32
•	GPS
•	HUD system
Bracelet:
•	Heart rate sensor
•	Temperature sensor
•	IMU
•	Battery
Communication:
•	Bluetooth Low Energy (BLE)
Advantages:
•	Less weight on the head
•	Larger battery
•	Better heart-rate measurements
•	Easier PCB design
Currently I will:
Build everything as a single prototype first.
After testing:
•	Evaluate comfort
•	Evaluate battery life
•	Decide whether a bracelet is necessary
Decision:
Keep this option open.

6. Is it possible to make the display appear/disappear using some sensor button?
Short answer:
Yes.
There are several possible implementations.
Option 1: Screen ON/OFF
Button Press:
Display turns ON
Button Press:
Display turns OFF
Advantages:
•	Saves battery
•	Simple implementation

Option 2: Change display modes
Mode 1:
Speed + Distance
Mode 2:
Heart Rate
Mode 3:
Temperature
Mode 4:
Battery
Advantages:
•	More information
•	Better user experience

Option 3: HUD Activation
Display remains off while running.
User presses button:
Display appears for several seconds.
Display automatically disappears afterward.
Advantages:
•	Lowest battery consumption
•	Less distraction
Currently we can:
Implement Option 2 first.
Later explore Option 3.
Decision:
Button functionality is absolutely feasible.

7. What IMU should we use?
Prototype IMU:
MPU6050
Reasons:
•	Cheap
•	Large community support
•	Easy to learn
•	Many tutorials available
•	Perfect for learning IMU concepts
Capabilities:
•	3-axis accelerometer
•	3-axis gyroscope
Can provide:
•	Step counting
•	Cadence estimation
•	Motion tracking
•	Head movement tracking

Final Project IMU:
BNO085 / BNO086
Reasons:
•	More accurate
•	Better sensor fusion
•	Better orientation estimation
•	Industry level wearable device performance
Can provide:
•	Orientation
•	Rotation
•	Running dynamics
•	Motion tracking
Advantages over MPU6050:
•	Less software complexity
•	Better results
•	More professional solution
Current recommendation:
Summer:
MPU6050
Senior Design Final Version:
BNO085 or BNO086
Decision:
Learn using MPU6050 and upgrade later.











Page 4: Team & Organization
8. Who Is Going to Be Our Fourth Teammate?
The fourth teammate should ideally contribute a skill set that complements the current team.
Option 1: Samy (we can still try and convince her to join us)
Advantages:
•	We already know her.
•	We trust her.
•	Easier communication and coordination.
•	Familiar with our working styles.
•	Cybersecurity background could be useful for:
o	Data privacy
o	Bluetooth security
o	Mobile application security
o	Future cloud connectivity
Potential concerns:
•	Need to verify her interest in hardware-oriented projects.
•	Need to verify her availability and commitment level.
Current recommendation:
Highest priority candidate.
 
Option 2 – Ignacy's ECE 362 Teammate
Advantages:
•	Potential embedded systems experience.
•	Possible PCB design experience.
•	Possible hardware debugging experience.
•	May strengthen the electrical engineering side of the project.
Potential concerns:
•	Unknown work ethic.
•	Unknown availability.
•	Need to evaluate team chemistry.
Current recommendation:
Worth discussing and evaluating.

Ideal Skill Sets for a Fourth Teammate
The most valuable addition would be someone with one or more of the following:
•	PCB Design
•	Embedded Systems
•	Mobile App Development
•	Bluetooth/BLE Experience
•	CAD / Mechanical Design
•	Optics / Display Systems
•	Computer Vision
•	Product Design
Current Team Gap:
The largest technical gap currently appears to be:
1.	PCB Design
2.	Mechanical Design
3.	Optics / HUD Systems
These areas should be prioritized when evaluating candidates.

9. Safety Considerations
Safety should be considered from the beginning of the project.
Physical Safety
•	Device should not obstruct vision.
•	HUD should not distract the runner.
•	Components should be securely mounted.
•	No sharp edges.
•	Comfortable weight distribution.
Electrical Safety
•	Proper battery protection.
•	No exposed wiring.
•	Proper voltage regulation.
•	Avoid overheating.
Running Safety
•	User must maintain awareness of surroundings.
•	Display should not overload the user's vision.
•	Emergency display shutoff should be available.
Future Considerations
•	Water resistance
•	Sweat resistance
•	Outdoor usability

10. GitHub, Communication, and Project Management
GitHub
GitHub will be used for:
•	Source code
•	Version control
•	Documentation backups
•	Project milestones
Current repository has already been created.
Team members should be added using both Purdue and personal accounts if necessary.

Notion
Current recommendation:
Use Notion as the primary project management platform.
Possible sections:
•	Tasks
•	Weekly goals
•	Research notes
•	Meeting notes
•	Documentation
•	Hardware tracking
•	Purchasing lists
Advantages:
•	Easy collaboration
•	Documentation
•	Progress tracking

Obsidian
Potential use:
•	Personal notes
•	Individual research
Not recommended as the primary team management platform.
Reason:
•	Less collaborative
•	More suitable for personal knowledge management


11. What Programming Language Should We Use?
Prototype Phase
Arduino C++
Advantages:
•	Easy to learn
•	Large community
•	Extensive sensor support
•	Fast prototyping
Current recommendation:
Use Arduino C++ during Summer 2026.

Advanced Development
ESP-IDF
Advantages:
•	Professional ESP32 framework
•	Better power management
•	Better multitasking
•	More scalable
Recommendation:
Transition after a working prototype has been completed.

Final Decision
Summer:
Arduino C++
After MVP:
Evaluate ESP-IDF migration.

12. What do we need to learn?
Hardware
•	ESP32 Architecture
Sensors
•	MPU6050
•	BNO085/BNO086
•	MAX30102
•	BME280
•	GPS Modules
Power Systems
•	LiPo Batteries
•	TP4056 Charging Modules
•	Battery Management
•	Power Consumption Analysis
Displays & HUD
•	OLED Displays
•	Micro OLED Displays
•	HUD Principles
•	Prism Optics
•	Optical Combiners
•	Waveguides
PCB Design
•	KiCad
•	EasyEDA
•	Schematic Design
•	PCB Layout
•	Manufacturing Process
Software
•	Arduino C++
•	ESP-IDF
•	Bluetooth Low Energy (BLE)
Future Topics
•	Mobile App Development
•	Data Visualization
•	Running Analytics
•	Product Design
•	Wearable Technology
Current Goal:
By the end of Summer 2026, I should have a working prototype capable of displaying:
•	Speed
•	Distance
•	Heart Rate
•	Temperature
using ESP32 and off-the-shelf components.













Technical Notes
ESP32 ADC
Ye ye, we guys are all smart, but it’ll be a great refresh to go through this part and remind ourselves everything that we have learned so far.
ESP32 contains a built-in 12-bit Analog-to-Digital Converter (ADC).
A 12-bit ADC can represent:
2¹² = 4096 values
Range:
0 → 4095
Example:
0.0 V → 0
1.65 V → 2048
3.3 V → 4095
Basically 3.3V/4096 = 0.805 mV is 1 byte/level
Purpose:
The ADC allows ESP32 to convert analog voltages into digital values that can be processed by software.
Potential uses in our project:
•	Battery voltage monitoring
•	Ambient light sensing
•	Future analog sensors

Communication Protocols
UART
Used for communication between two devices.
Typical use:
GPS → ESP32
Pins:
•	TX (Transmit)
•	RX (Receive)

I2C
Allows multiple devices to communicate using only two signal wires.
Pins:
•	SDA (Serial Data)
•	SCL (Serial Clock)
Current planned devices:
•	MAX30102
•	BME280
•	MPU6050
•	SSD1306 OLED

SPI
High-speed communication protocol.
Pins:
•	MOSI
•	MISO
•	SCK
•	CS
Planned future use:
•	Micro OLED HUD display
•	Advanced IMU
•	SD card storage

IMU
IMU = Inertial Measurement Unit
Purpose:
Measures motion and orientation.
Contains:
•	Accelerometer
•	Gyroscope
Prototype:
MPU6050
Final Version:
BNO085 / BNO086
Possible Running Metrics:
•	Cadence
•	Head movement
•	Acceleration
•	Running dynamics

PWM
PWM = Pulse Width Modulation
Used to simulate analog output using digital signals.
Potential uses:
•	Vibration motor intensity
•	LED brightness
•	Future display brightness control
Example:
100% Duty Cycle = Full Power
50% Duty Cycle = Half Power
25% Duty Cycle = Quarter Power

BLE
BLE = Bluetooth Low Energy
Purpose:
Communication between glasses and smartphone.
Potential transmitted data:
•	Heart rate
•	Speed
•	Distance
•	Battery level
•	Temperature
We will care about this part later
