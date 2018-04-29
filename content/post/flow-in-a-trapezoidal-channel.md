---
title: "Flow in a Trapezoidal Channel"
date: 2018-04-29T09:38:33+08:00
draft: false
tags: ["tutorials", "python", "hydraulics", "open channel"]
image: "images/trapezoidal_channel.jpeg"
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
from channelflowlib.openchannellib import Trapezoidal

# Initialize Trapezoidal Channel instance
trap = Trapezoidal(unknown='discharge')
```

In the above snippet, we have opened the file openchannellib from the channelflowlib package and imported Trapezoidal class.

We then initialised the class giving it the unknown=’discharge’. The available unknowns in this library are [‘discharge‘, ‘water_depth‘, ‘channel_slope‘, ‘channel_base‘]. If the unknown is not specified in the constructor, the default will be used which is the water_depth.

In this particular problem, we have the given as follows:

- Unknown = Channel Discharge
- Bed Slope = 0.001
- Side Slope = 1:1
- Channel Base Width = 1.0 meter
- Manning n = 0.015
- Depth of water = 0.989 meter

Now we are going to set the available inputs:

```python
# Set the inputs
trap.set_channel_slope(0.001)
trap.set_sideslope(1.0)
trap.set_channel_base(1.0)
trap.set_roughness(0.015)
trap.set_water_depth(0.989)
```

After the inputs have been set, we are now going to use the analyze() method to calculate for the unknown.

```python
# Analyze
trap.analyze()
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
# Discharge : 2.67
# Wet Area : 1.967
# Wet Perimeter: 3.797
# Hydraulic Radius: 0.518
```

### Setting the unit
The default unit in channelflowlib for rectangular channel is metric. To change this to english (e.g. feet for lengths), it must be set on the instantiation.

```python
trap = Trapezoidal(unknown='discharge', unit='english')

# Anything aside from 'metric' that is set to 'unit' will be treated as
# non-metric units which will automatically be english.
```
