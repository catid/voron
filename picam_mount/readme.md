## Voron V2 Pi Camera Mount

![Completed Install](https://github.com/catid/voron/raw/master/picam_mount/installed.jpg "Completed Install")

![Camera View](https://github.com/catid/voron/raw/master/picam_mount/camera_view.jpg "Camera View")

## Materials:

Electronics:

+ Official Raspberry Pi Camera Module V2 8-megapixel sensor 3280 × 2464 1080p V2.1 for Raspberry Pi 3 2 1 model B B+
+ Arducam CSI to HDMI Cable Extension Module with 15pin 60mm FPC Cable for Raspberry Pi Camera Specific (Pack of 2, 1 Set)
+ 3 foot (1 meter) HDMI cable.
+ You might need a slightly longer PiCam MIPI cable to reach from the adapter to the camera.

Fasteners:

+ Small screws that come with the HDMI adapters and PiCam - Do not throw these away!  If you lost some you can use 2-3 screws instead of 4 and share between the mounts.
+ 2x m3 Heatset insert
+ 2x m3x12
+ 2x m3x8
+ 3x 2020 T-nut insert
+ Some double-sided tape to secure the MIPI cable

## Prints:

One of each of the STLs included:

+ `2020Mount.stl` : Attaches to gantry on the side under the Z cable chain.
+ `PCBHolder.stl` : Bolts to the 2020Mount and carries the Pi camera.  Small screws that come with the Pi can secure it down.
+ `CaseTop.stl` : Bolts to the PCBHolder and provides some protection for the camera.
+ `PiCamHdmiAdaptMountBay.stl` : Attaches to the side of any open 2020 extrusion near the Pi.  Terminates HDMI cable, provides PiCam CSI ribbon cable.
+ `PiCamHdmiAdaptMountGantry.stl` : Attaches to gantry on the top behind the Z cable chain, flush against the AB motor housing.  Terminates PiCam CSI ribbon cable, provides HDMI cable.

## Assembly:

Install heatset inserts into the two holes in the 2020Mount.

Install the two HDMI adapters into their mounts with their tiny bolts.

Bolt one to the top of gantry (with T-nut), and route the HDMI cable through the Z cable chain.  Bolt the other one into the electronics bay (with T-nut) close enough to the Raspberry Pi so that a CSI ribbon cable will reach to the (center) CSI port on the Pi.
Note that the one for the gantry will send the HDMI cable to the right, while the one for the electronics bay sends HDMI the wrong way for use on the gantry.

Bolt 2020Mount onto side of gantry (with T-nut) between Z cable chain.

Attach Pi camera to the HDMI adapter via ribbon cable.

Bolt PCBHolder to 2020Mount first, and then install the Pi camera with tiny bolts.
Bolt CaseTop to PCBHolder.
