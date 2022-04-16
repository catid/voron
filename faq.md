## Motor is losing steps:

So there are a few common causes for motors to lose steps.  First off, disable motor power and move the toolhead along both diagonals by hand.  Not in X/Y direction: 45 degrees so that only one motor spins at a time.  You should feel the same resistance both ways.  If one side is even slightly harder to move, then check if that belt path is wrapped around a post in the back.  It may also not run through the center of the pulleys, idlers, and bearings in the gantry and be rubbing on the sides.  You might find belt dust accumulating somewhere, or see wear on the sides of the belts.
Another thing that can happen is your grub screws have come loose on one of the AB motors.  You can make this easier to check by buying some CrossCheck and pasting a little line across the pulley/rotor that will break if the grub screws are loose.
It could also be that the crimps on the wires going to the AB motors are not tight, so during motion the motors are losing power.  This one is harder to diagnose but might happen more or less if you wiggle the cables.
Finally you might have an issue in the printer.cfg motor settings.  For example the run_current might need to be set higher to achieve the speeds you are requesting without missing steps.

## Motor is not spinning:

If a motor is not spinning, is stuttering, or causing Klipper errors then it is likely not wired properly.  To fix it you can use a multimeter to figure out how it should be wired, since the colors or positions of the wires from the motor do not mean anything.
First make sure that your printer is powered off!  An easy test is to take a multimeter and press the probe to the first two pins on the JST-XH connector, after removing it from the mcu.
You should see close to 0 ohms resistance that increases to ~11 ohms or so after a while.  Then test the next two pins (BB) and check again.  Final check the center pins to make sure you get infinite resistance (open circuit).
If you find that it's wired ABBA, then the easiest fix is to use one end of some tweasers to press under the pin housing and release the JST crimp clasp to allow the pins to slide out, use your fingernail to prop the crimp clasp back up so it will hold tight in the new hole.  With this method, swap two pins on the JST connector so that there is no need to re-crimp.

## Motors are noisy at higher speeds:

Make sure Stealthchop is turned off.

## How to configure motor current:

Setting run_current higher helps reduce the noise from the printer, and it will unlock faster speeds.  Do you know what the rated current is, or type of A and B motors you're using?  Typically you want 85% of the RMS current.  For LDO 0.9 degree steppers that are rated for 2A peak - divide by sqrt(2) - that means 1.41A RMS and 1.2A at 85%.  For 1A motors used for extruder, people tend to use 0.5 in Klipper for run_current.

## How to configure motor microsteps:

Setting microsteps higher reduces noise from the printer and may help unlock faster speeds.  You can increase motor microsteps until the mcu starts printing a mcu timer error in the Klipper logs.  LDO 0.9 degree steppers seem to max out around 128 microsteps, while 1.8 degree steppers max out at 256.

## No MGN12 rail:

If you do not have a MGN12H rail but instead two MGN9H rails for the X axis, you'll want the 2.4 parts for the X axis XY joints rather than the 2.4r2 ones.  You can find them under STLs/Superceded_Parts/MGN9_X.
For the rest of the printer you can use the improved 2.4r2 parts, and you can reference the 2.4r2 assembly manual and other docs during your build.

## Belts rubbing on the side panels:

The side panels need to have 3mm foam tape (weather stripping) applied around the perimeter so that the gantry belts do not rub on them.

## Improved side/top panel clips:

There are options for bolted, magnetic, and locking corners.  The bolted ones are a pain to take on and off.  The magnetic ones tend to fall off very easily in practice, so are not recommended.  The locking corner clips are excellent and require no fasteners or magnets to build:
https://github.com/Annex-Engineering/Other_Printer_Mods/tree/master/All_Printers/Annex_Panel_2020_Clips_and_Hinges/panel_clips_and_corners/

The corners are under `corner/STL`, and should be sized to the panel+foam tape width.  For example for 3mm top panel with 1mm foam tape, you'd use the 4mm corner piece x4.  And for the sides you might have 3mm panels with 3mm foam tape, so 6mm corner pieces.
Similarly you'd need to print the keys from `key/STL` sized appropriately for your panels.

To avoid gaps in the side panels, you can also print a few `single/STL` that twist lock onto the middle of the side panels.

It's also a good idea to buy some Plexus plastic cleaner, because it makes the panel surface much more slick, more clear, and better at resisting dust.

## Improved door panels:

There are a few options for the door panel hinges.  I've found that the hinges with the smoothest motion are found here:
https://github.com/Annex-Engineering/Other_Printer_Mods/tree/master/All_Printers/Annex_Panel_2020_Clips_and_Hinges/hinge/screw_mount/R4_625/STL
These require M5x40mm bolts, 12 625 bearings (not the flanged ones), and 24 m5 1mm spacers/washers (to make them even smoother).  3 on each side will provide plenty of support for the tape supporting the panels while they are open.

To provide some support for the doors and allow them to be easily latched down, I'd recommend printing a snap-latch-2020 for the top and bottom of each door panel: https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/richardjm/snap-latch-2020

## Adding handles:

The best handles I've found are the Sturdy Handles, since these stay clear of the panels and do not need to be removed if the panels are removed:
https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/jeoje/Sturdy_Handles

## Kits:

Buying a kit to build a Voron may take longer than self-sourcing and can be more expensive.  You will wait longer for the kit to arrive, and some of the parts will not be the best ones for your build, or may be unreliable where you need quality: e.g. SSR or inductive probe.  So you may end up buying some parts twice if you order a kit.  It's best to buy subkits from vendors you can find on the Voron Discord under the VENDORS section - Just google the store name and search to see what they offer, and you'll find subkits for parts that you need that will ship faster than from China and often with higher quality.
Ordering the cable chains directly from IGUS on digikey.com is a good idea, as they ship quickly and I've had trouble with intermediate vendors selling kits at a markup not including the right parts.

## Wires in cable chains:

The wires going through the chains should be PTFE and not be twisted or have anything else like zip-ties on them.  The reason to keep it simple is to avoid kinks forming that will cause the cables to break after a while.
Silicone wire is not as good as PTFE for cable chains mainly because PTFE cables are self-lubricating and slide past eachother in the cable chains, and they're also smaller diameter so it's easier to run the cables through.

## Warning about Loctite:

Loctite eats away ABS plastic and will cause it to become brittle.  Only use Loctite on metal parts (inside T-nuts or bolts, on grub screws) and in small amounts.  The damage it causes to plastic parts is not obvious visually, and it's worth replacing parts that were accidentally exposed to Locktite.

## Tuning overhang cooling to fix sagging:

Probably you need more fan speed when printing overhangs.  The settings in SuperSlicer are `Filament Settings > Cooling > Bridges fan speed = 82%` to set the speed of the fan and `Print Settings > Perimeters & Shell > Overhangs > threshold for [X] Bridge speed and fan: 40%` to set the angle at which the bridge fan speed is used.
To tune it I would recommend using the SuperSlicer `Calibration > Filament Temperature Calibration` test print and pay attention to the overhang part to determine the angle at which you need more fan.  And then do a bunch of test prints at different fan speeds to find the settings that work for your filament and printer.  You may find that a higher or lower nozzle temperature may perform better overall.

## How to tune SuperSlicer Extrusion Multiplier and Klipper pressure_advance:

The simple way to calibrate EM/PA is to run a grid search with lots of generated cubes using your normal printing speed and settings.  In SuperSlicer, Generate > FreeCAD and enter cube(30, 30, 0.45).  Copy the cube 5 times and edit each one: Right-click a cube, Add Settings > Filament > Extrusion multiplier  and assign each one a different EM multiplier from 0.98, 0.99, 1.0, 1.01, 1.02.

While printing, pay attention to any of the perimeters to tune PA.  If the perimeter lines do not touch, then your PA is too low and you can slowly tune it higher.  If the corner lines do not touch, then your PA is too high and you can slowly tune it lower.

After the print finishes, feel the tops of the cubes.  If they feel rough parallel to the lines, then EM is too high.  If they feel rough perpendicular to the lines, then EM is too low.  They should feel smooth in both directions.  Your favorite cube indicates how to adjust the EM, -2% to +2% around the current EM in your print settings.  Just multiply the EM multiplier by what you have and update it.  Then do it again until you're happy with the smoothness. 

## Genuine Gates Pulleys/Idlers:

According to Ellis' tuning guide using genuine parts for the XY gantry is a good idea for print quality: https://github.com/AndrewEllis93/Print-Tuning-Guide/blob/main/articles/troubleshooting/vfas.md

https://www.filastruder.com/products/gates-2gt-pulley?variant=15443750518855
https://www.filastruder.com/products/gates-2gt-idler?variant=15443755728967

## The mainsailos.local domain does not resolve in the browser:

You may need to install Bonjour services on your Windows computer: https://support.apple.com/kb/DL999?locale=en_US
You can also edit the hostname of your Pi in sudo raspi-config then 1 System Options > S4 Hostname so you can give it a more fun name
