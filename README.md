# JCW-Pro-Exhaust-Controller

this simple project was born from the personal need to solve an annoying problem with the bluetooth remote control of my JCW Pro exhaust. I am not responsible for any damage to third parties or objects, including the car. This publication is for the sole purpose of my memory.

The exhaust valve is controlled by a 12v powered control unit located in the trunk. The control unit is not a simple relay, the valve is controlled by a PWM circuit and opens / closes according to the supplied voltage. Not having an oscilloscope I was not able to determine the duty cycle of the PWM control, however by jumpering the control signal to GND I saw that the valve actually opens. Therefore, by inserting a relay after the control unit, it is possible to remotely control the jumper.
