---
title: "Hydroflow"
date: 2019-02-22T14:22:25+08:00
draft: false
categories: ["projects"]
tags: ["hydraulics engineering", hydraulics", "projects", "dub library"]
---

**hydroflow** is a dub library for the D programming language. The library is for the hydraulics engineering calculations. This page will show the development documentation of the project as well as some showcases if there may be available.

### Day 1 - January 15, 2019
- This is the first day and first commit of the project to the public repository Github.
- The creation of the hydroflow module for the public imports of all necessary access to the library so that the library need only a single import, hydroflow module.
- The base class OpenChannel was also started to define public, private and protected properties.
- Contains the initial setter and getter methods.

### Day 2 - January 19, 2019
- Derivative of the base class OpenChannel, RectangularOpenChannel was started. Also a sample implementation was tested.
- The first solver completed was the calculation of the unknown discharge.

### Day 3 - January 20, 2019
- Input validation and error handling was first implemented for the RectangularOpenChannel.

### Day 4 - January 25, 2019
- First draft of the class RectangularOpenChannel was completed.
- Errors and bugs are yet to be determined.

### Day 5 - January 27, 2019
- Class TrapezoidalOpenChannel was created.

### Day 6 - January 28, 2019
- Solver for unknown water depth created for RectangularOpenChannel.
- Solver for unknown base width created for RectangularOpenChannel.
- Solver for unknown bed slope created for RectangularOpenChannel.
- Cloned the RectangularOpenChannel contents to TrapezoidalOpenChannel.
- Updated method for calculation of unknown discharge for TrapezoidalOpenChannel.

### Day 7 - January 29, 2019
- Added error and input checking for side slope for TrapezoidalOpenChannel.
- Updated formula for the wetted area and perimeter of TrapezoidalOpenChannel.