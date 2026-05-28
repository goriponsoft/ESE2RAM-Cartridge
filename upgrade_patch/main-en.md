# Circuit board modification information

This information concerns upgrading circuit boards from Rev.6 and earlier to Rev.7 equivalent.
Previous Rev.6 boards had circuits that put a strain on the MSX console, so this upgrade is strongly recommended.
<br>This will make the circuit equivalent to Rev.7, reducing the strain on the console, improving battery life, and enhancing compatibility.

Please note that the actual modification has been verified on boards from Rev.4 to Rev.6. It may not be possible to perform the modification using the same procedure on boards from Rev.3 or earlier.

## Parts list
|Contents|Quantity|
|:--|--:|
|resistor 3.3K ohm, 1/4W|1|
|Schottky barrier diode BAT43<br>*If a replacement is needed, please select a diode with a low forward voltage (Vf) (usually a Schottky barrier diode).|3|
|MLCC 100pF, 50V|1|
|EC 47uF, 6.3V or higher|1|
|jumper wire|Appropriately|

## Circuit board modification procedure

Here are the actual repair procedures.

1. Pattern Cutting (Frontside of Circuit Board)
<br>Perform pattern cutting.
<br>Cut the patterns indicated by the red lines in the image (3 locations, 4 wires).

![](cut_front.png)

2. Pattern Cutting and Component Removal (Backside of Circuit Board)
<br>Similar to the front side, pattern cutting is performed, and in addition, D1, D2, R3, and R4 are removed.
<br>Cut the patterns indicated by the red lines in the image (7 locations, 7 wires), and remove the components enclosed by the orange lines (4 locations).

![](cut_back.png)

3. Component Installation and Jumper Wiring (Backside of Circuit Board)
<br>Based on the actual wiring diagram below, place the components and connect the jumpers with wiring material.
<br>Replace R3 and R4 with BAT43 diodes (see image for orientation), replace D2 with a BAT43 diode (same orientation as the original), and bypass D1 by connecting it with wiring without placing any components.
<br>Connect the 100pF MLCC in parallel with the BAT43 placed in the original R3 location.
<br>Connect the negative side of the 47uF EC to the original D1 cathode (GND) and the positive side to the D2 cathode. Please note that there is a protrusion on the inside of the case near the horizontal line around R3 and R4, so if you place the EC there, the case may not close.

![](patch_back.png)

## Actual modification example

These are photos of the actual modification and verification process.
<br>Incidentally, the pattern cuts were made by drilling out the relevant areas.
<br>In the actual wiring diagram, there are pins (SRAM's VCC/GND) that are connected in a different location and via a different path than in this photo, to prevent the wiring from overlapping and becoming difficult to see.

![](photo_back.png)
