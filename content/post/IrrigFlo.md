---
title: "IrrigFlo"
date: 2018-05-08T19:43:11+08:00
draft: false
categories: ["projects"]
image: "images/irrig_flo.jpeg"
---

**IrrigFlo** is an open source java software that aims to be an alternative to commercial hydraulics softwares like Bently's FlowMaster and others.

The project will be written in java from scratch including all the core libraries.

This page will serve as the timeline documentation of the project and will be updated as often as the project's push to the repository.

### Day 1 - May 7, 2018
- I started structuring the project and the library at day 1 trying to make something work for SVP (Smallest Viable Product).
- Started the class 'OpenChannel', this is the base class of all open channels.
- Started the class 'RectangularOpenChannel' which is a child of OpenChannel class.

### Day 2 - May 8, 2018
- Continue work on the library and incorporating some implementations.
- Stays at 'RectangularOpenChannel' class.
- I also started writing exception handling at this stage. I don't know when you should be doing that but I did it anyway.

### Day 3 - May 9, 2018
- Improve the exception handling
- Added two (2) constructors for RectangularOpenChannel class, 1st with unknown as parameter, 2nd is unknown and the rest of inputs.
- This time I started to compile the library into a jar file and used in another project just to see if it works, it does.
- To add a little spice, the graphical user interface has been drafted.
![alt text](/images/irrig_flo_first_gui_draft.JPG "First draft of the UI")

### Day 4 - May 11, 2018
- Start work on TrapezoidalOpenChannel class, for trapezoidal channel calculations.
- Written the essential codes for the class.
- Below is a sample problem solved using an online calculator.
![alt text](/images/day28/trapezoidal_channel_sample_problem.png "Sample Problem")
- Below is the sample implementation of the class
![alt text](/images/day28/trapezoidal_channel_implementation.png "Implementation")
- Below is the result of the sample implementation. Can be compared with the result in the sample problem.
![alt text](/images/day28/trapezoidal_channel_result.png "Result")

### Day 5 - May 12, 2018
- Completed critical flow analysis on trapezoidal open channel
![alt text](/images/day29/critical_flow.png "Critical flow")
