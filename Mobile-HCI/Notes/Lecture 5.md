---
tags:
  - Lecture
  - MHCI
---
---
# Location-Based Interaction
Device location changes often and can give user context

Location sensing could allow:
- exploration
	- finding things nearby
- navigation
	- how to get to destination
- suggestions
	- similar to exploration but ig push notif
- lcoation sensitive behaviour
	- smart home interaction when arrive or leave home

Location is
- position on planet
- position in a room or building
- proximity to a know device - meters from home hub

### Sensing Methods
approaches:
- GNSS - GPS subset of GNSS
- Access point - cell or wifi router
- beacon/tag - bluetooth UWB beacons
- optical sensing - fiducial marker (qr codes), visual inertial SLAM
- multimodal - google fused location, apple core location

### GNSS
in terms of degrees with (latitude, longitude)
![[long-lat.png]]
show that we refernce longitude from greenwich and then latitude from the equator

**Accuracy**
variance
- 10cm (BeiDou)
- 20cm (Galileo)
- 30cm (GPS)

Line of sight from the multiple satalites can cause variance, many buildings or objects that will block radiowaves will affect this.

### Elevation
GNSS makes it hard to get elevation of devices.

Most devices use a barometric pressure sensor to determine elevation. This takes air pressure to determine elevation on the base that air pressure decreases as you increase height above sea level.

### Access Point Trilateration
cross referencing with network access point locations - if we have known position like mobile cell tower, wifi access points.
can get accuracy of 5-15m

### Indoor Positioning
Access Point Trilateration becomes a feasible solution for indoor position.
Issue: Precision and accuracy is low. It is subject to noise due to objects, people etc. also when a strong signal is expected a problem becomes the 5 to 15m precision

### Indoor Positioning via Proximity
Absolution is difficult
indoor position can be better estimated by using proximity reading from other devices.

### Beacons and Tags
small emitters that use bluetooth or UWB radio
with enough of them you can mesh them in network allowing great precision and accuracy directions

### RSSI
Relative Signal Strength Indication
- Measure the power of radio signal

Issue: assumes consitents attenuation - not true since radio signal will be affected by objects "line of sight stuff"

### ToF
Time of Flight
measure duration between signal emission and reception
radio waves travel at known speed so can measure distance,
determines proximity

### AoA
In an antenna that has multiple reception we can also determine angles relative to emitter.

### Performance
RSSI matches outdoor location finding - 2-5cm
AoA improves high precision with - 10-50cm. However is still gaining adoption

### UWB
signals pass through solid objects
uses ToF so cannot determine direction for emmiter however with a large meshed network it is possible to use trilateration

### Fiducial Marker Tracking


### Relative Movement
Sensors can understand change in location without knowing location and by taking the difference.

motion sensor monitor device acceleration, orientation etc
cannot reliably determine change in position due to drift

**Visual SLAM**
Using optical sensors to detect features in environment
- creates like a data point cloud associating depth and with each point to allow position in relation to what it sees
**Google Project Tango, Oculus Insight**

### Requesting Location Data
Consider update rate and battery
- how often do we need to pull this info? 1s, 10s, 100s
some devices restrict rate - sports wearable typical 1hz to 0.1hz for GNSS

Platforms enforce sensible rates too - android restricts apps not in use

### Processing Location Data
Accommodate for the variability and noise
- standing still - jumps around
- straight line walk - zig zags, rubber bands

Signal processing can improve quality
- applying heuristics to remove outliers
- applying smooth filters, moving averages
- fusing with other sensor data - improves confidence

### Google FLP
Use multimodal signal processing already, since there is issues surrounding building reflecting signals.
Google uses photogrammetry to create models of urban areas.

### Simple Filtering Methods
Moving average
Weighted Moving Average
Exponential weighted moving average

### Kalman Filtering
Commonly used with fast moving sensors

Fusses data with prediction of future movements
Sometimes multimodals with inertial measurement data

Initially developer for car apps
- cars make smooth fast trajectories
- use this to correct GNSS

Make app specific assumptions - when cycling you can expect both road and path routes, not true for cars.

### Interaction Techniques
Proximity
- being near point arises event for a function

Geofencing
- If inside a region described then do some action

### Privacy Case Study: Strava
Workout app for tracking activity. Users upload location data, also includes physiological, photo data etc.

Many privacy concerns
- way data is used
- lack of user engagement in privacy controls

**Strava Heatmap**
Aggregates all activity from data
shows where users often ride and run

Useful for finding popular run and cycles
Integrated into oute creation tools

**Concerns**
Individual users, household identifiable.
Bike theifs have a field day

Human error
Heatmap revealed a US Army base - since most strava users are westerners deployed army members in afghan revealed a army base.

**Location + Time**
Time stamps show where and when, shows habits, when your house might be empty
**Fly-By**
Users you passed on trips. Can cause issue with unknown features

### Shared Responsibility
Users?
- Should be aware when giving access and what that implies
Strava - software devs?
- should educate users