## MEAN WELL 48V PSU Stack

![Assembled Stack](https://github.com/catid/voron/raw/master/meanwell_psu_stack/assembled.jpg "Assembled Stack")

Because the stack is too tall for the bottom panel, I'm planning to leave off the bottom panel.

This is intended to be used for stacking a second 48V PSU on top of the first PSU in a Voron 3D printer.
My 250mm Voron is not large enough to mount a second 48V PSU in the electronics bay, and I was not able to find PSUs that were smaller and also provided enough power.

There is a 20mm offset between the two PSUs for airflow.  Both PSUs should have active cooling.  The MEAN WELL 200W PSUs do not have active cooling but the 350W versions do, and they ship fast and are fairly cheap and have good build quality.

Added an extra 20mm to the Voron feet so that the second PSU does not hit the ground, and so that it can breathe.

## Materials:

Electronics:

+ 1x Actively Cooled MEAN WELL 24V PSU.  350W version works.
+ 1x Actively Cooled MEAN WELL 48V PSU.  350W version works.

Fasteners:

+ 8x m4x6 bolts

## Prints:

+ 1x `MeanwellStackLeft.stl`
+ 1x `MeanwellStackRight.stl`
+ 2x `FootSpacerAx2.stl`
+ 2x `FootSpacerBx2.stl`

They should fit on a 250mm build plate.

## Assembly:

Install using the m4x6 bolts so that the terminals are exposed as in the picture above.  Then install as normal using the typical Voron mounting option.

The bottom panel should be left off with this mod, since the stack is too tall.

The normal Voron feet spacers should be replaced by the thicc ones, which add an extra 20mm of height under the printer so that the 48V PSU can breathe and so that it doesn't hit the floor.
