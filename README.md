# EBYTE_ESP32-S3
<b>Last updated as of PCB testing iteration "V1.5"</b>

This is an 8-layer board which uses JLCPCB's JLC08161H-2116 to base the controlled impedence calculations for the USB data lines. For 5 pieces the cost is less than $5 shipped due to their promotional offer, ordering mass quantities (400+) comes to approximately 1 USD each final effective price, but other manufacturering options are possible. This board focuses on being compact and portable, having a 50x50x9mm footprint with the antenna and power cable disconnected.

Photos from the 3D render of EasyEDA Pro don't show the plating/solder mask (and epoxy fill) of vias. The actual PCB doesn't have holes where these 0.3mm and 0.4mm inner diameter vias are, and also has 'via-in-pad's.

## Tips
This board is capable of outputting a claimed 30 dBm though ~29.5 dBm is more realistic. Make sure you respect local regulations, more information, also regarding how the software works with the board, is in the variant.h file found in [this directory](https://github.com/meshtastic/firmware/tree/master/variants/EBYTE_ESP32-S3). Check the [output power of the E22-900M30S](https://github.com/S5NC/EBYTE_ESP32-S3/blob/main/power%20testing.txt), albeit on a different board and at the default US frequency. Most notably, the power was measured from an additional IPEX connector that went through the board using a via, the actual power output is probably very slightly higher if using the on-board IPEX connector or a direct SMA connector on the same layer.

RP-SMA is preferred even though it is less common in Europe, as it ensures there is no change of having a void connection between an SMA female board and RP-SMA male antenna. Also, with insertions the pin the slot end is worn more than the pin, it's easier to change antenna or antenna connector than replace the soldered connector on the board.

Especially if using the board SMA-style connector, use an bendable antenna, or one with a lead cable, as to enable the adjustment of the antennas orientation.

More tips can be found on the text of the schematic and PCB silkscreen, as well as the Document layer of gerber file.

## Next steps

More future possibilities for improvements are on the schematic.

The ESP32 is very power hungry compared to the nRF52840, especially for Bluetooth. Powered by 5.2 V, this board will draw ~100 mA when the Bluetooth is turned on and receiving, and ~650 mA when transmitting (and Bluetooth powered on) (technically this should be 750 mA, 100 mA + 650 mA from the E22-900M30S's datasheet). Using a DC-DC converter could give some improvement for the 3.3 V powered device (ESP32, and any I2C devices and/or GPS you add). Making a way to turn the Bluetooth off after a time interval with no connection has passed, and turning it back on when a button (such as the BOOT) is pressed, could be used but only if the device can be physically accessed. If it is mounted on top of a pole, this would not work. Other options may be putting the ESP32 into a power saving Bluetooth mode if such thing exists, and listening for a beacon packet from a phone which would like to scan for nearby boards?
