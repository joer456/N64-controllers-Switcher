# N64-controllers-Switcher

The N64 Controllr Switcher is a tool to enable seemless controller switching without needing to unplug anything.
These can be made with input display built in using an Arduino and [RetroSpy](https://github.com/retrospy/RetroSpy).

# What you will need
- 2x [N64 Controller Extension Cable](https://s.click.aliexpress.com/e/_olXS8Bv)
- 1x [SPDT Switch](https://s.click.aliexpress.com/e/_opt6h0X)
- 1x (Optional for Input Display) ATMEGA328 Based Arduino (or Clone) I have had good results with the [LGT8F328P-LQFP32](https://s.click.aliexpress.com/e/_onnZ7X5)

# Wiring
![n64controllerpinout](https://ezhid.sourceforge.net/n64pad.png)
- Here is a crude wiring diagram
- <img width="1772" height="783" alt="image" src="https://github.com/user-attachments/assets/89bde62b-a37c-4d41-b083-a67c0e1e64f8" />
- First, cut the 2 female ends of the extentsion cables off and use some wire strippers to exposse the 3 internsl wires. Also strip the end of the cable on the male side.
- <img width="800" height="423" alt="image" src="https://github.com/user-attachments/assets/8741fe55-5f1a-4973-9a8b-425630231953" /> 
- You will need to connect all of the N64 3.3v wires together (These are typically soldered with red wires)
- Next do the same for the GND wires (Typically black wires). If you are adding Input Display be sure to connect the GND to the Arduino as per the schematic  
- For the switch, connect the data lines from the female ports(typically white or green wires) to the outer pins of the SPDT switch and then connect the male data line to the centre pin (and Arduino pin D2 if adding Input display)


# Firmware (RetroSpy input display)
- Download the latest [RetroSpy release](https://github.com/retrospy/RetroSpy/releases)
- Install the latest [Arduino IDE](https://www.arduino.cc/en/software/)
- Open the `firmware.ino` file from the RetroSpy download and remove the `//` from `//#define MODE_N64` to enable N64 mode within RetroSpy
- Connect your arduino and upload the firmware
- When using RetroSpy, you may need to select `Don't filter COM Ports` from the Options menu
