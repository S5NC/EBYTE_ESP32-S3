# EBYTE_ESP32-S3
<b>Last updated as of PCB testing iteration "V1.3"</b>

This is an 8-layer board which uses JLCPCB's JLC08161H-2116 to base the controlled impedence calculations for the USB data lines. For 5 pieces the cost is less than $5 shipped due to their promotional offer, ordering mass quantities (400+) comes to approximately 1 USD each final effective price, but other manufacturering options are possible. This board focuses on being compact and portable, having a 50x50x9mm footprint with the antenna and power cable disconnected.

Photos from the 3D render of EasyEDA Pro don't show the plating/solder mask (and epoxy fill) of vias. The actual PCB doesn't have holes where these 0.3mm and 0.4mm inner diameter vias are, and also has 'via-in-pad's. 

## Tips
This board is capable of outputting a claimed 30 dBm though ~29.25 dBm is more realistic. Make sure you respect local regulations, more information is in the board's variant.h file found in [this directory](https://github.com/meshtastic/firmware/tree/master/variants/EBYTE_ESP32-S3).

RP-SMA is preferred even though it is less common in Europe, as it ensures there is no change of having a void connection between an SMA female board and RP-SMA male antenna. Also, with insertions the pin the slot end is worn more than the pin, it's easier to change antenna or antenna connector than replace the soldered connector on the board.

Especially if using the board SMA-style connector, use an bendable antenna, or one with a lead cable, as to enable the adjustment of the antennas orientation.

More tips can be found on the text of the schematic and PCB silkscreen, as well as the Document layer of gerber file.

## Next steps

Future possibilities for improvements are on the schematic.
