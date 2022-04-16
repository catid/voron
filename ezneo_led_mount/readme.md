## Voron V2 ezNeo LED Brackets

Designed to be used with the ezNeo LED boards:
https://www.th3dstudio.com/2021/07/16/add-rgb-to-your-3d-printer-with-our-ezneo-kits/



## Prints:

You will need 3x `ezNeoLEDbracket.stl` for each board.

## Assembly:

Insert heatset inserts into the larger hole on each bracket.

Bolt the brackets to the board, and then bolt the brackets+board to the 2020 frame.

Extra step requires soldering and crimping connectors:
To chain the ezNeo boards together, use multimeter to find the SignalOut, Vin, and GND pins at the end of the board, and solder a pigtail that can be connected to the next board.
This way you can use just 3 cables to connect the LEDs to your mcu, which usually only has one LED port.

Extra step requires a drill (and ideally a center punch):
You can buy some diffusers that are the width of these boards and drill holes in them to mount with the m3x8 bolts.
