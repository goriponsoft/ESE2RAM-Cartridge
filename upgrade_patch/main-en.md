# Circuit board modification information

This information concerns upgrading circuit boards from Rev.6 and earlier to Rev.7 equivalent.
Previous Rev.6 boards had circuits that put a strain on the MSX console, so this upgrade is strongly recommended.
<br>This will make the circuit equivalent to Rev.7, reducing the strain on the console, improving battery life, and enhancing compatibility.
The modification involves two stages: patching the circuit board to create a circuit equivalent to Rev.7 by using jumpers, pattern cuts, and discrete components, and replacing the IC. There are three possible modification methods: performing only one of these steps, or performing both.
<br>However, because the former patching involves soldering jumpers and discrete components to the IC pins, if you patch first, you may need to remove the patch once it's installed. Therefore, if you plan to replace the IC, it is recommended to do so first.

>[!IMPORTANT]
>The actual modification has been verified on Rev.4 to Rev.6 circuit boards. It may not be possible to modify Rev.3 or earlier circuit boards using the same procedure.

## Parts list
|Contents|Quantity|
|:--|--:|
|Resistor 3.3K ohm, 1/4W|1|
|Resistor 10K ohm, 1/4W<br>*Not required if the removed items are to be reused.|1|
|Schottky barrier diode BAT43<br>*If a replacement is needed, please select a diode with a low forward voltage (Vf) (usually a Schottky barrier diode).|5|
|MLCC 100pF, 50V|1|
|EC 47uF, 6.3V or higher|1|
|Logic IC "74ACT138"<br>*If you want to replace the IC|1|
|jumper wire|Appropriately|

## Circuit board modification procedure

Here are the actual repair procedures.

0. IC replacement
<br>We will remove the U3 and replace it with an IC from the ACT family that we have prepared.
- Remove the part enclosed by the orange line (one location) and replace it from 74AHC138 to 74ACT138.
- While replacing the ICs will provide maximum compatibility, it is usually not necessary. For models that operate faster than standard MSX (such as the FS-A1FX/WX/WSX in 5.37MHz mode or the HC-90/95 in turbo mode), models with different bus timing than standard MSX (such as the 1chipMSX series or the HC-90/95), or models with different signal drive voltages than standard MSX (such as the 1chipMSX series), compatibility may be further improved compared to modifications alone. Please choose the appropriate option based on the machine you are using.

![](remove_front.png)

1. Pattern cutting (front side of circuit board)
<br>Perform pattern cutting.
- Cut the patterns indicated by the red lines (two locations) in the image.

![](cut_front.png)

2. Pattern cutting and component removal (backside of circuit board)
<br>Similar to the front side, pattern cutting will be performed, and in addition, D1, D2, R1, R3, R4, and the jumper pins will be removed (the 1024KB/512KB switching jumper pin will become unusable after this modification).
- Cut along the red lines (9 locations) in the image, and remove the components (6 locations) enclosed by the orange lines.
- It may be difficult to see, but please note that there are also places to cut on the left side of R1 (between the left pad and the IC pins) and between the jumper pins (if jumper pins are installed, they should already be cut).

![](cut_back.png)

3.Jumper wiring (front side of circuit board)
<br>Based on the following wiring diagram, create a jumper (1 wire) using wiring material.
- Since this involves soldering to the terminals of the card edge connector, please take care to prevent too much solder from flowing by covering the terminals with heat-resistant tape or similar means.

![](patch_front.png)

4. Component mounting and jumper wiring (backside of circuit board)
<br>Based on the following wiring diagram, place the components (9 locations) and connect the jumpers using wiring materials.
- Connect the cathode side of the BAT43 to the left pad of R1, and the anode side of the BAT43 to pin 22 of the SRAM (just above the left pad of R1). Connect one end of the 10kΩ resistor to the right pad of R1, and the other end of the resistor to the anode side of the BAT43.
- Replace R3 and R4 with BAT43 diodes (see image for orientation), replace D2 with a BAT43 diode (same orientation as the original), and bypass D1 by connecting it with wiring without placing any components.
- Connect the anode of the BAT43 to the left pad of the jumper pin (the side with the square silkscreen printing), and connect the cathode of the BAT43 to the right pad. If you install it vertically, it won't fit in the case, so please install it horizontally.
- Connect the 100pF MLCC in parallel with the BAT43 placed in the original R3 location.
- Connect the negative side of the 47uF EC to the original D1 cathode (GND) and the positive side to the D2 cathode. Please note that there is a protrusion on the inside of the case in the horizontal area around R3 and R4, so if you place electrolytic capacitors there, the case may not close properly.
- The connection of the SRAM pin on the far left of the physical wiring diagram is a reconnection to GND, so any GND will work, and in the physical wiring diagram, the solder mask of a nearby GND plane is scraped off and the connection is made there.

![](patch_back.png)

## Actual modification example

These are photos of the actual modification and verification process.

![](photo_back.png)
![](photo_front.png)
