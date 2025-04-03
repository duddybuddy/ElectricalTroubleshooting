# ElectricalTroubleshooting
- Use a golden unit for comparison whenever possible (unless you only have one, and there is a risk of breaking it, then be very careful)
- If a board is hand assembled, there is a great chance that you have a workmanship issue
  - Backwards components, incorrect component placement, accidental DNI/installation of a DNI, open pin(s), absolute decimation of silicon from too much heat, solder bridges
- When troubleshooting a protocol (i2c, SPI, CAN) with an oscillocope, trigger on the nominal signals, as you'd expect to see them, and then try moving your triggers to the outskirts of the where the signals should be
  - short pulses, long pulses
  - voltages that are too high/low
- logic analyzers and scope decoders are amazing, use em
- When you have a voltage present in a system that you would not expect to be present, try loading it with a light load to see if it can deliver current at the measured voltage
- low current devices that are drawing too much current:
  - improper configuration of MCU (pull ups/downs, peripherals, etc.)
  - board contamination
  - leaky capacitors
  - damaged silicon
  - backpowering of ICs through protection circuitry on pins
- Be careful poking around, hotplugging connectors, injecting voltages from power supplies (high capacitance can lead to a lot of energy delivered quickly)
- Diode mode on your meter can reveal nuances that an ohmmeter can not. This is especially true when comparing a questionable unit to a known good unit.
- If you have a board to board system, be careful when swapping a problematic board with a good board into a system... the system could have been the reason your problematic board is not working... 

## Test Equipment
- When measuring the outpput of a function generator with an oscilloscope... it is easy to trick yourself/measure the wrong amplitudes if the function generator is set up to deliver a signal to a 50ohm terminated device. Some scopes have a switchable termination, some function generators have a "High-Z" output mode, and other times, you might need to add a terminator to your signal chain.
