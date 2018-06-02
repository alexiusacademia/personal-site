---
title: "IrrigFlo"
date: 2018-05-08T19:43:11+08:00
lastmod: 2018-05-20
draft: false
categories: ["projects"]
image: "images/irrig_flo.jpeg"
description: "A java library for solving hydraulics engineering problems."
tags: ["java library", "hydraulics engineering", hydraulics", "projects"]
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
<img src="/images/day28/trapezoidal_channel_sample_problem.png" width="600" alt="sample problem" />
- Below is the sample implementation of the class
<img src="/images/day28/trapezoidal_channel_implementation.png" width="600" alt="implementation" />
- Below is the result of the sample implementation. Can be compared with the result in the sample problem.
<img src="/images/day28/trapezoidal_channel_result.png" width="600" alt="result" />

### Day 5 - May 12, 2018
- Completed critical flow analysis on trapezoidal open channel
<img src="/images/day29/critical_flow.png" width="600" alt="critical flow" />

### Day 6 - May 13, 2018
- Published a release on github v1.0.0
<img src="/images/day30/1st_release.png" width="600" alt="First release"/>

### Day 7 - May 14, 2018
- Working on CircularOpenChannel class for solving circular pipes that are not flowing full.
- Stuck on the critical flow in circular channel

### Day 8 - May 15, 2018
- Finally solved the bug in the critical flow of the circular open channel.
- The problem is in the written function that gets some parameters that are not in the critical flow!
- Published new version of the library v1.1.0
<img src="/images/day32/2nd_release.png" width="600" alt="second release" />
<img src="/images/day32/sample_problem.png" width="600" alt="sample problem" />
<img src="/images/day32/implementation.png" width="600" alt="implementation" />
<img src="/images/day32/result.png" width="600" alt="result" />

### Day 13 - May 20, 2018
- Continue work on the library particularly on the IrregularSectionChannel class
- Finished coding and testing of the normal flow on irregular sections
<img src="/images/day36/irrig_flo_1.png" width="600" alt="Implementation" />
<img src="/images/day36/irrig_flo_2.png" width="600" alt="Implementation" />
<img src="/images/day36/irrig_flo_3.png" width="600" alt="Result of normal flow on irregular section channel" />

### Day 15 - May 22, 2018
- Continue on the library
- Completed the feature for irregular section channels
- Published a release of the library v1.2.0
<img src="/images/day38/v1.2.0.png" width="600" alt="Release IrrigFlo v1.2.0" />
