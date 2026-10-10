# AC-Defender
This is a simulation based AC peripheral protection circuit driven by Arduino UNO. It can protect the peripheral from Over Voltage, Under Voltage, Over Current or Under Current situation. Any voltage or current spikes triggers the device which saves the peripheral. It has a status monitor and onboard control system along with computer connectivity.

#Features:
True RMS Measurement: Calculates accurate RMS voltage and current over 20ms sample windows.

OLED User Interface: Real-time system status, voltage, and current display.

Interactive Menu System: Navigate and set custom safety thresholds directly from the device.

Smart Button Logic: Differentiates between short presses (navigate/cancel) and long presses (save).

EEPROM Persistence: Saves your custom threshold settings permanently so they survive power cycles.

PC Terminal Control: Monitor real-time data and configure thresholds remotely via Serial monitor.

SRAM Optimized: Extensively uses the F() macro to keep dynamic memory footprint low and prevent simulation crashes.
