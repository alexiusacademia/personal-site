---
title: "Channel Flowlib"
date: 2018-04-29T10:37:42+08:00
draft: false
image: "images/channel_flowlib.png"
categories: ["projects"]
tags: ["projects"]
---
ChannelFlowLib is a python library that can be used as aid in solving hydraulic calculations for open channels. It uses the Manning’s equation in solving the hydraulic elements.

This project aims to create bits of modules for hydraulics engineering and later to be combined as one package for easier distribution. It aims to create an open source software for this subject to help both engineering students and instructors if they ever find this useful to them.

There are four types of open channel classes in this module; rectangular, trapezoidal, circular and for irregular sections as well.

Here are the current features of this library:

- Rectangular Open Channel
- Trapezoidal Open Channel
- Circular Channel (Not flowing full)
- Irregular Channel (For streams)

### Notes
- In the circular pipe class in the module open channel, I haven’t incorporated yet the unit conversion. All units are assumed to be in metric. Although it’s easy to incorporate it if you are to use it by subclassing it and override the getter and setter functions.
- Both circular and irregular section classes uses metric only. Feel free to override the getters and setters of those classes to apply unit conversions.
- Here are some assumptions/constraints in the IrregularSection class.
 - Only the left and right sides should be higher than water surface elevation.
 - Coefficient of roughness is uniform in the entire section.
 - Placement of points in the class constructor is properly sorted.

### Additions
---
###### 08/03/2016
- IrregularSection class has been added to the openchannellib module.

###### 08/03/2016
- Uploaded a module irrig_channel. This module will calculate the discharge-elevation rating curve. Note that this module is not yet incorporated as a class in **Open Channel** module. This is a separate file for separate use.

###### 10/29/2017
- Module irrig_channel is deleted. This is replaced by a more standardized code examples.

### Installation
```python
pip install channelflowlib
```

### Usage
###### Rectangular Channel
```python
from channelflowlib.openchannellib import Rectangular

# Initialize Rectangular Channel instance
rect = Rectangular(unknown='discharge')

# Set the inputs
rect.set_channel_slope(0.001)
rect.set_channel_base(1.0)
rect.set_roughness(0.015)
rect.set_water_depth(0.989)

# Analyze
rect.analyze()

# Show the outputs
print ('Discharge : ', round(rect.discharge, 2))
print ('Wet Area  : ', round(rect.wetted_area, 3))
print ('Wet Perimeter: ', round(rect.wetted_perimeter, 3))
print ('Hydraulic Radius: ', round(rect.hydraulic_radius, 4))
```

###### Irregular Section
```python
from channelflowlib.openchannellib import  IrregularSection
import matplotlib.pyplot as plt

# Create tuple of points (tuple)
pts = (
    (0, 1.13),
    (1.287, 1.2),
    (2.58, 0.09),
    (5.223, -1.57),
    (10.446, -1.81),
    (12.333, 0.72),
    (14.188, 1.2)
)

# Initialize the channel with the points
channel = IrregularSection(pts)

# Set the required inputs
channel.set_average_rougness(0.03)
channel.set_bed_slope(0.002)
channel.set_water_elevation(1.0)
channel.analyze()

# Print some outputs
print('Discharge : ', round(channel.discharge, 2))
print('Wet Area  : ', round(channel.wetted_area, 2))

# Plot a water rating curve
# This requires matplotlib
max_elev = 1.0
min_elev = -1.0
interval = 0.1
intervals = ((max_elev - min_elev) / interval)

elevs = []
discharges = []

for i in range(int(intervals) + 1):
    elev = min_elev + (i * interval)

    channel.set_water_elevation(elev)
    channel.analyze()

    discharge = channel.discharge

    elevs.append(elev)
    discharges.append(discharge)

plt.plot(discharges, elevs)
plt.show()
```

<center>Output of the plot.</center>

<img src="/images/channel_flowlib.png" width="640"/>
