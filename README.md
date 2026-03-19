================================================
SPS-QUAD-120: SMART 4-CHANNEL POWER DISTRIBUTION UNIT
================================================
OVERVIEW
The SPS-QUAD-120 is a high-reliability power management platform designed for 
robotics, industrial automation, and high-current embedded systems. It 
combines heavy-duty physical protection with 16-bit digital telemetry via 
I2C, providing a bridge between raw power distribution and intelligent 
system monitoring.

SYSTEM ARCHITECTURE & POWER FLOW
--------------------------------
* Centralized Power Input: High-current power enters through a dedicated 
  heavy-duty terminal and is distributed across four independent channels.
* Precision Current Sensing: Each channel features a 2mOhm high-side shunt 
  resistor to minimize voltage drop while capturing accurate data.
* Digital Power Monitoring: Sense lines interface with a specialized 16-bit 
  Power Monitoring IC to calculate real-time current, voltage, and power.
* I2C Communication: All telemetry data is accessible via a standard I2C 
  interface for integration with Arduino, ESP32, or STM32 controllers.

DUAL-LAYER HARDWARE PROTECTION
------------------------------
1. Layer 1 (Physical): Redundant Fusing
   Each output path is protected by dual blade-style fuses, providing a 
   robust physical failsafe against overcurrent or short-circuit events.

2. Layer 2 (Transient): TVS Suppression
   Every channel includes a high-power TVS (Transient Voltage Suppressor) 
   diode at the output stage to clamp voltage spikes and protect sensitive 
   downstream electronics from inductive kickback.

TECHNICAL SPECIFICATIONS
------------------------
Feature                | Specification
-----------------------|-------------------------------------------------------
Input Voltage          | 5V - 36V DC (Nominal)
Number of Channels     | 4 Independent High-Side
Monitoring Resolution  | 16-bit Voltage, Current, & Power
Sensing Method         | High-Side Shunt (2mOhm)
Communication Protocol | I2C Interface
Primary Protection     | Dual Blade Fuses (per channel)
Secondary Protection   | High-Power TVS Diode (per channel)
-----------------------|-------------------------------------------------------

REPOSITORY CONTENTS
-------------------
/Hardware : Schematics (PDF), PCB Source Files, and Bill of Materials (BOM).
/Docs     : Theory of Operation and Component Datasheets.
/Firmware : Example libraries and scripts for I2C data retrieval.

PROJECT GOAL
------------
Standard fuse blocks are "blind." The SPS-QUAD-120 provides the telemetry 
needed to predict failures, profile power consumption, and protect 
expensive hardware with industrial-grade transient suppression.

===============================================================================
Designed for high-reliability power monitoring and distribution.
