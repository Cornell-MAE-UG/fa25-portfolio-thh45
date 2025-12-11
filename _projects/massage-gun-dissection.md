---
layout: project
title: Massage Gun System Dynamics Analysis
description: Dissection and control system analysis of a massage gun for MAE 3260
technologies: [MATLAB, Oscilloscope, System Dynamics, Control Systems]
image: /fa25-portfolio-thh45/assets/images/massage-gun-cover.jpg
---

<style>
img {
  max-width: 800px;
  width: 100%;
  height: auto;
}

h1 {
  font-size: 1.8em;
  line-height: 1.2;
}

h2 {
  text-align: left;
  margin-left: 0;
}
</style>

## Project Overview

For MAE 3260 (System Dynamics), our team analyzed the dynamic behavior and control system of a Homedics massage gun. This dissection project investigated how the device transitions between operating modes and the underlying control mechanisms that enable responsive performance.

**Team Members:** Toby Huynh, Alexander Barry, Charles Valembrun, and Abha Bhole

---

## Assignment Objective

The goal of this project was to:
- Dissect a consumer electromechanical device
- Analyze its dynamic system behavior using oscilloscope measurements
- Develop transfer function models and block diagrams
- Investigate transient response characteristics
- Understand real-world control system implementation

---

## What We Did

### 1. System Dissection & Component Analysis
We disassembled the massage gun to identify key components:
- DC motor with offset cam mechanism
- Lithium-ion battery pack
- Pulse Width Modulation (PWM) controller circuit
- Linear linkage converting rotary motion to oscillation

### 2. Experimental Setup
We developed two measurement approaches:
- **Accelerometer testing:** Taped accelerometer to massage gun tip to measure vibration response
- **Voltage measurement:** Direct oscilloscope connection to DC motor terminals to capture PWM signals

### 3. Key Findings

**Operating Modes Discovered:**
- **Slow Mode:** 21.5 Hz frequency, 0.371 V amplitude (in free air)
- **Fast Mode:** 42.6 Hz frequency, 1.024 V amplitude (when pressed against surface)
- **Transition:** Nearly instantaneous mode switching triggered by applied force

**PWM Duty Cycle Analysis:**
- Slow mode operates at 44% duty cycle
- Fast mode operates at 84% duty cycle
- Transition completes in approximately 7 milliseconds
- Surprisingly linear duty cycle ramp (expected exponential behavior)

### 4. Control System Modeling

We developed a block diagram representation showing:
- Closed-loop feedback control responding to mechanical disturbance
- PWM controller adjusting motor voltage based on load detection
- Mass-spring-damper mechanical system with transfer function: G(s) = 1/(ms² + bs + k)

The fast mode likely operates near (but not at) the system's resonant frequency to maximize amplitude while avoiding structural instability.

---

## Technical Analysis

The massage gun demonstrates sophisticated disturbance rejection control:
1. Applied force creates mechanical load on the tip
2. Controller detects increased motor resistance
3. PWM duty cycle rapidly increases to compensate
4. Higher average voltage produces faster motor speed
5. Oscillation frequency and amplitude increase proportionally

This closed-loop behavior explains why the device automatically delivers a more intense massage when pressed against the body - the applied force acts as both a disturbance input and a mode trigger.

---

## Full Report

For detailed experimental methods, oscilloscope data, mathematical analysis, and complete results, view our full dissection report:

**[Download Full Report (PDF)](https://cornell-mae-ug.github.io/fa25-portfolio-thh45/assets/3260_Dissection_Report.pdf)**

---

## Conclusions

This project revealed the elegant control system design within a consumer product. The massage gun uses PWM control, load sensing, and near-resonant frequency operation to deliver effective therapeutic vibration while maintaining mechanical stability. The rapid mode transition and disturbance rejection demonstrate practical implementation of feedback control principles studied in MAE 3260.
