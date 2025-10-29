#  Accurate Digital Clock Using Arduino

This project demonstrates how to build a **simple yet accurate digital clock** with **date functionality** using an **Arduino** and a **16x2 I2C LCD display**.
It does **not require an RTC (Real-Time Clock) module**, making it a cost-effective and educational way to understand software-based timekeeping.


## Overview

The clock keeps track of **hours, minutes, days, months, and years** entirely through Arduino’s internal timing system.
Although it doesn’t use an RTC, it includes a **speed adjustment feature** to compensate for clock drift, ensuring accurate long-term operation.

---

##  Features

*  **Time Display:** Shows the current time in **24-hour format**.
*  **Date Display:** Displays the current **day, month, and year**.
*  **Manual Time & Date Setting:** Easily set or adjust time and date using buttons.
*  **Speed Adjustment:** Fine-tune timing accuracy to counter Arduino’s internal clock drift.
*  **Optional Buzzer:** Audible feedback during setting or alerts.

---

## Components Required

| Component                | Quantity | Description                                  |
| ------------------------ | -------- | -------------------------------------------- |
| Arduino Board (Uno/Nano) | 1        | Main controller                              |
| 16x2 LCD Display (I2C)   | 1        | For displaying time and date                 |
| Push Buttons             | 3        | For mode, hour/day, and minute/month control |
| Buzzer (optional)        | 1        | For audible feedback                         |
| Jumper Wires             | —        | For connections                              |
| Breadboard               | 1        | For assembly                                 |

---

## Circuit Connections

| Component               | Arduino Pin        | Description                           |
| ----------------------- | ------------------ | ------------------------------------- |
| **LCD (I2C)**           | SDA → A4, SCL → A5 | Display connection                    |
| **Mode Button**         | D2                 | Switch between modes                  |
| **Hour/Day Button**     | D3                 | Increment hour/day/year               |
| **Minute/Month Button** | D4                 | Increment minute/month/decrement year |
| **Buzzer (optional)**   | Any digital pin    | Audible alert (optional)              |

---

## Modes of Operation

| Mode                      | Description                                 |
| ------------------------- | ------------------------------------------- |
| **Show Time Mode**        | Displays current time and date              |
| **Set Time Mode**         | Allows user to adjust hours and minutes     |
| **Set Date Mode**         | Allows user to adjust day and month         |
| **Set Year Mode**         | Allows user to set the year                 |
| **Speed Adjustment Mode** | Adjusts correction factor for time accuracy |

---

## Button Functions

| Button           | Pin | Function                                         |
| ---------------- | --- | ------------------------------------------------ |
| **Mode**         | 2   | Cycles through available modes                   |
| **Hour/Day**     | 3   | Increments hour/day/year or increases correction |
| **Minute/Month** | 4   | Increments minute/month or decreases correction  |

---

## Setup Instructions

### **Hardware Setup**

1. Connect the **16x2 I2C LCD** to the Arduino (`SDA → A4`, `SCL → A5`).
2. Connect the three **buttons** to pins **2**, **3**, and **4** with appropriate pull-down or pull-up resistors.
3. (Optional) Connect a **buzzer** for sound feedback.

### **Software Setup**

1. Install the following libraries:

   * `Wire.h`
   * `LiquidCrystal_I2C.h`
2. Upload the provided Arduino code to your board.

### **Initial Configuration**

* Use the **Mode button** to switch between settings.
* Set the **time**, **date**, and **year** using the respective buttons.
* Adjust the **speed correction value** to improve accuracy.

---

## How It Works

* The Arduino uses **timer interrupts** to maintain precise timekeeping in milliseconds.
* A **Julian date calculation** ensures correct date handling (including leap years).
* A **speed correction factor** is used to counter slight inaccuracies in the Arduino’s internal oscillator.

---

##  Usage

* The clock automatically runs once powered on.
* Use the **buttons** anytime to update the time or date.
* Periodically adjust the **speed correction** for optimal long-term accuracy.

---

## Notes

* The clock’s accuracy depends on the **stability of the Arduino’s oscillator**.
* Use the **speed adjustment mode** to fine-tune drift correction.
* Ideal for learning **software-based timekeeping** and **LCD interfacing** without an RTC module.
