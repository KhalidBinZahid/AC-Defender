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


#Protection Logic:

Over-Current (Permanent Lockout): If the current exceeds the maximum limit, the relay instantly cuts power and the system locks down to prevent electrical fires. Requires a hard reset to restore.

Over/Under Voltage (Auto-Recovery): If the voltage goes out of bounds, the relay cuts power. Once the grid stabilizes, the system waits for a 10-second safety cooldown before automatically restoring power.

Under-Current (Warning): If the current drops below the minimum threshold, the display flags an UNDER CURRENT warning, but leaves the relay ON.

#Simulation Environment: Built and tested in Proteus 8.13.

#Key Components:

Microcontroller: Arduino Uno (R3)

Display: OLED12864I2C (Connected to A4/SDA and A5/SCL)

Relay: Standard SPDT Relay for load switching (Pin 7)

Voltage Sensing: Step-down transformer with a 2.5V DC biasing circuit (Pin A0)

Current Sensing: Simulated ACS712 using a Current Controlled Voltage Source (CCVS) with a 2.5V DC bias (Pin A1)

#Navigation & Control: The system uses three push buttons: MENU, UP, and DOWN.

Navigate Menus: Short press MENU to select an option. Use UP/DOWN to move the cursor.

Adjust Values: In the edit screen, use UP/DOWN to change the threshold value.

Save Settings: HOLD the MENU button for 1 second to save the new value to EEPROM.

Cancel Edit: SHORT PRESS the MENU button while editing to discard changes and go back.

#Setup:

Clone this repository.

Open the .ino file in the Arduino IDE.

Install the required libraries via the Library Manager:

Adafruit GFX Library

Adafruit SSD1306

Compile and Export the compiled Binary (.hex).

Open the Proteus 8.13 project file.

Double-click the Arduino Uno component, point it to your new .hex file, and press Play!
