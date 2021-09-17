PID Controller

ESP32 Async WebServer WebSocket JSON PID Controller Thermostat

Code is a mix of collected and modified projects from github.

Spetial thanks to Stéphane Calderoni who inspired me with his two projects:

https://github.com/m1cr0lab-esp32/remote-control-with-websocket

https://github.com/m1cr0lab-esp32/asynchronous-web-controlled-thermostat

As a result we got example of one solution for PID Controller with visualization in a Web browser.

The Controller have 8 channel of digital input + 8 channel of digital output + 1 input for zerocross detection + 1 PWM output which is PID controlled output.

Digital inputs and outputs are independent of the PID calculator and work as independent.

Digital inputs wait HIGH PULSE on each channel to control each channel of outputs in parallel with the Web Interface as a physical and virtual button.

Physical Button connected to input I_01 toggle Q_01, also Web Interface button Q_01 also toggle output Q_01 on ESP32 through WebSocket protocol.

I_01 OR WEB Q01 -> OUTPUT Q_01

I_02 OR WEB Q02 -> OUTPUT Q_02

I_03 OR WEB Q03 -> OUTPUT Q_03

I_04 OR WEB Q04 -> OUTPUT Q_04

I_05 OR WEB Q05 -> OUTPUT Q_05

I_06 OR WEB Q06 -> OUTPUT Q_06

I_07 OR WEB Q07 -> OUTPUT Q_07

I_08 OR WEB Q08 -> OUTPUT Q_08

PID control PWM Output by setting Setpoint, Kp,Ki,Kd,Mode,Output,Offset parameters in Web Interface.

Parameter Output can set output (0-100%) only in MANUAL MODE (2 or 5). The purpose of this parameter is for commissioning of the system that are being controlled.

PID Controller by default is Automatic Heating Mode with Standard PID algorithm but this can be changed through code to different mode like


HEATING AUTO STANDARD -> 0

HEATING AUTO PARALLEL -> 1

HEATING MANUAL        -> 2

COOLING AUTO STANDARD -> 3

COOLING AUTO PARALLEL -> 4

COOLING MANUAL        -> 5


Parameter Offset is offset for sensor reading to calibrate all sensors in system to same refernce point.

Simple and useful for Home Automation Projects.

Feel free to be inspired and make improve of this project, and if you like to support this project feel free to contact me through mail:

ucontrollerlab@gmail.com


![ESP32_Async_PID_Thermostat_v2_3](https://user-images.githubusercontent.com/90904958/133772109-7fdc4e6f-088f-494a-8c6e-5d74eb77e80d.PNG)


