# gameKey PCBs #
![gameKey PCBs](/docs/MainControlPCB.png)

This repo contains the main control board and thumb cluster board for gameKey devices.

The main board provides headers for a SparkFun Pro Micro to break into a diode key matrix, the analog inputs for the thumbstick, a mode switch (NYI), addressable LED (NeoPixel, WS2811, etc) (NYI), and a hardware kill switch to allow reflashing in case of some kind of firmware problem. It can either be hand assembled with 30x SOD-323 1n4148 diodes or ordered with PCB Assembly from JLCPCB (recommended).

The thumb cluster PCB is very simple, acting as a backing board and breakout for the navigation switch and joystick.

## Main PCB ###

Main PCB Wiring: **The Enable header MUST be populated and shorted with a jumper to enable the firmware to output anything.**

The addressable LED will only work if you are using a 5V/16MHz Pro Micro. D is the Data pin, 5V is in the center, and GND is on the - label.

Each finger goes to it's nearest pads (for a left hand gK), with side buttons going to C5 in either configuration. Buttons are assigned from closest to the palm [R0] out to the end of the knuckle[R4], in order.

In the 'standard' configuration, used by your left hand, Pinky is on C0, Ring is on C1, Middle is on C2, Index is on C3, Nav Switch is on C4, and Index[R0]/Pinky[R1] Sides/Joystick push[R2]/Thumb Side[R3] buttons are on C5.

In the 'mirrored' configuration, used by your right hand, Pinky is on C4, Ring is on C3, Middle is on C2, Index is on C1, Nav Switch is on C0, and Index[R0]/Pinky[R1] Sides/Joystick push[R2]/Thumb Side[R3] buttons are on C5.

## Thumb Cluster PCB ##
The stick is an Alps RKJXV122400R, and the navigation switch is an E-Switch JS5208 5 position. NavSwitch is wired to the Main Control in the order N[R0], E[R1], S[R2], W[R3], Push[R4] as labeled on the Thumb Cluster PCB.

### Error in Thumb Cluster PCB fixed on Sept 6, 2023 ##
Previous to 9/6/2023, there was an error in the thumb cluster PCB where the navigation switch was lacking its common/column pin and was tied to ground. If you have an older PCB, you can work around this by cutting the trace from Pin 1 of the JS5208 pads and wiring it directly between that pin and C4. New PCBs have a pad for C(olumn) marked on the bottom silkscreen.

![gameKey PCBs](/docs/PCBError.png)
