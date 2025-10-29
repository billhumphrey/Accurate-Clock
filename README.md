# Accurate-Clock


Overview
This project demonstrates a simple clock with date functionality using an Arduino and a 16x2 LCD display. The clock does not require an RTC (Real-Time Clock) module, making it an affordable and straightforward solution for basic timekeeping needs. The project is designed by Prince Kushwaha from COSM Electronics.

# Features
Time Display: Shows the current time in 24-hour format on a 16x2 LCD.
Date Display: Shows the current date.
Time and Date Setting: Allows the user to set the time and date using buttons.
Speed Adjustment: Compensates for the Arduino clock drift to maintain accurate time.
# Components
Arduino Board: Used to control the clock and manage the display and buttons.
16x2 LCD Display: Displays the current time and date.
Buttons:
Mode Button (pin 2): Toggles between modes (set time, set date, and run).
Hour/Day Button (pin 3): Increments the hour and day.
Minute/Month Button (pin 4): Increments the minute and month.
Buzzer (optional): Can be added for audible feedback.
# Modes of Operation
Show Time Mode: Displays the current time and date.
Set Time Mode: Allows setting of the current time.
Set Year Mode: Allows setting of the current year.
Set Date Mode: Allows setting of the day and month.
Set Speed Adjustment Mode: Allows adjustment of the speed correction for the Arduino clock drift.
# Button Functions
Mode Button (pin 2): Cycles through the different modes.
Hour/Day Button (pin 3):
In Set Time Mode: Increments the hour.
In Set Date Mode: Increments the day.
In Set Year Mode: Increases the year.
In Set Speed Adjustment Mode: Increases the correction value.
Minute/Month Button (pin 4):
In Set Time Mode: Increments the minute.
In Set Date Mode: Increments the month.
In Set Year Mode: Decreases the year.
In Set Speed Adjustment Mode: Decreases the correction value.
# Setup Instructions
Hardware Connections:

Connect the 16x2 LCD display to the Arduino using the I2C interface.
Connect the mode button to pin 2.
Connect the hour/day button to pin 3.
Connect the minute/month button to pin 4.
(Optional) Connect a buzzer to an appropriate pin for audible feedback.
# Software Setup:

Install the necessary libraries for the LCD display (Wire.h and LiquidCrystal_I2C.h).
Upload the provided code to the Arduino.
Initial Configuration:

After powering up, use the mode button to navigate to the "Set Time" and "Set Date" modes to configure the current time and date.
Adjust the speed correction value if necessary to ensure accurate timekeeping.
# Usage
Once set up, the clock will run continuously, displaying the current time and date.
Use the buttons to adjust the time and date as needed.
The speed correction mode can be used to fine-tune the clock's accuracy.
# Notes
The project uses a Julian date calculation method to handle date operations.
The timer interrupt is configured to maintain an accurate millisecond count for timekeeping.
Speed correction is necessary due to the inherent drift in the Arduino's clock.
