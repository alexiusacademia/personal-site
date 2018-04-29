---
title: "Calculate Flow in a Rectangular Channel"
date: 2018-04-29T08:56:44+08:00
draft: true
tags: ["tutorials", "python", "hydraulics", "open channel"]
image: "images/rectangular_channel.png"
---

Flow calculation is critical specially for hydraulics engineers. There are numerous commercial softwares available on the market to does the job. But what if there are few open source softwares that can do the job as well?

In this article, we’ll see how we can solve flow on a rectangular open channel using an open source python library called channelflowlib. This library can be used by a developer if he/she is planning to have open channel flow feature on a hydraulics software.

For now, we will be using python to use this library. At this point, it is assumed that you have a basic python knowledge and has python installed in your computer. The steps will be detailed as follows:

### Installation
```python
pip install channelflowlib
```

Now that we have channelflowlib installed, we can import it in our script.

```python
from channelflowlib.openchannellib import Rectangular

# Initialize Rectangular Channel instance
rect = Rectangular(unknown='discharge')
```

In the above snippet, we have opened the file openchannellib from the channelflowlib package and imported Rectangular class.

We then initialised the class giving it the unknown=’discharge’. The available unknowns in this library are [‘discharge‘, ‘water_depth‘, ‘channel_slope‘, ‘channel_base‘]. If the unknown is not specified in the constructor, the default will be used which is the water_depth.

In this particular problem, we have the given as follows:

- Unknown = Channel Discharge
- Bed Slope = 0.001
- Channel Base Width = 1.0 meter
- Manning n = 0.015
- Depth of water = 0.989 meter

Now we are going to set the available inputs:

```python
# Set the inputs
rect.set_channel_slope(0.001)
rect.set_channel_base(1.0)
rect.set_roughness(0.015)
rect.set_water_depth(0.989)
```

After the inputs have been set, we are now going to use the analyze() method to calculate for the unknown.

```python
# Analyze
rect.analyze()
```

Now if all values are validated, the unknown that we set will be solved. We can also retrieve some more public informations like wetted area, wetted perimeter, hydraulic radius etc.

To show the output,

```python
# Show the outputs
print ('Discharge : ', round(rect.discharge, 2))
print ('Wet Area  : ', round(rect.wetted_area, 3))
print ('Wet Perimeter: ', round(rect.wetted_perimeter, 3))
print ('Hydraulic Radius: ', round(rect.hydraulic_radius, 4))

# Outputs will be
# ('Discharge : ', 1.0)
# ('Wet Area  : ', 0.989)
# ('Wet Perimeter: ', 2.978)
# ('Hydraulic Radius: ', 0.3321)
```

### Setting the unit
The default unit in channelflowlib for rectangular channel is metric. To change this to english (e.g. feet for lengths), it must be set on the instatiation.

```python
rect = Rectangular(unknown='discharge', unit='english')

# Anything aside from 'metric' that is set to 'unit' will be treated as
# non-metric units which will automatically be english.
```
