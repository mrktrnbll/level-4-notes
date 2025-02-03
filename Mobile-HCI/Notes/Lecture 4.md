---
tags:
  - MHCI
  - Lecture
---
# Sensing Techniques
smart phones have loads of onboard sensors... Accelerometer, gyro, magnetometer temp, LIDAR iris scanner etc
- security - biometric password stuff
- ar - LIDAR, radar etc
- rotation - accelerometer and gyro

### IMU
inertial measurement unit is used to sense types of motions

### Immediate surroundings
* ambient light
* proximity
* camera
* depth
* bluetooth

### Position
- barometric pressure - elevation
- GNSS - GPS, GLONASS, GALLILEO etc
- bluetooth UWB: nearby devices

### 3D
- radar
- LIDAR
- Depth - measuring intensity of reflected infared light
- ultrasound measuring intensity of reflected sound

### More
- microphone, camera, touchscreen

### Sensor Fusion
Good in isolation for catching user context and input intention

BETTER when used together, can infer with more confidence if using multiple input modals

# Touchless Gesture: Case Study
Include mid-air gestures:
- **low-effort** interaction - skip song with swipe
- **less precision** - needs only gesture rather than tap exact button
- **input space** - increased over small screen
- **can't touch** - cooking eating driving etc
- **input state** - 'hover' content preview (samsung)
- **expressive** - can take of hand shape or finger used extra

### 1D Sensing
SideSight -
1D infared sensors detect the distance of finger from side of screen this could then be used to give mouse or trackpad like input.![[1D - infared.png]]

### 2D proximity
HoverFlow - expands on SideSight
![[2D - infared.png]]

Image shows that sensor see more reflective inference from the hand when hovered above the sensors - can be used to take input

### Magnetic Field Sensor
![[Screenshot 2025-02-03 at 15.36.35.png]]

Similar as infared for expects extra finger magnet attachment

### 3D sensing with radar
This is shown by good motion sense in pixel 4. Detects hand motion with radar.

### Challenges
- How do user know what gestures are
- How do they know where to perform them - depth from screen
- How do users know if they are gesturing correctly
- when wrong how do users solve problem
- How do they improve gestures

**Solves**
Feedback to user on incorrect input or "unkown" input gesture
User training - google made gestures a "gated" feature, allowing them to give training to users when first enabling the gesture features.

# Pressure Input: Case Study
Why would you use pressure:
- Adds extra input state
- Passive grip to active input 
- One handed input - answer call when phone detects hard grasp
- Eyes free input - squeeze in pocket to ignore call

# Single FSR
Performed by Graham Wilson et al at UofG
Found that 10 discrete levels of pressures could be applied effectively by users to illicit function

### Multiple FSRs
Graham Wilson expanded the work to use multiple level pressure from grip

# Input Recognition
Sensors provide continuous data that we need to effectively gate to binary

Input recognition requires looking patterns in data

**Challenges**
False-positive and false-negative recognition

### Approaches
Thresholding
Pattern
Machine Learning

Problems:
between users the level of inputs can vary but mean the same thing, size of hands, strength to grip the phone etc
- scale independance
- dynamic time wrapping - accounts speed of actions

Sensor capability
- low frame rate blurs fast motions
- low resolution observes less details

Segmentation
continous time series analysis makes it difficult to determine when a action begins or ends
- think about your hand before and after a 'swipe' - is it still swiping? kinda!

Training data - machine learning
- training data is bad at generalising between sensor technology
- sensor and platform
Calibration for specific users?
- common approach is to individualise recognition

