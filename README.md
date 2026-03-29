# STM32-SineWave-Display
A sine wave visualization project using STM32F103C8T6 and ST7789 TFT display. Demonstrates waveform generation, grid plotting, and smooth pixel-based rendering on embedded systems.
#  STM32 Sine Wave Display on TFT (ST7789)

##  Project Overview

This project demonstrates how to generate and display a **sine wave** on a TFT screen using the STM32 Blue Pill.

Instead of reading real signals, the waveform is mathematically generated using the sine function and then plotted on the display. This project helped me understand how waveform visualization works before building a real oscilloscope.

---

##  What I Learned

* How to interface **ST7789 TFT display using SPI**
* Pixel-level graphics drawing on embedded systems
* Generating waveforms using mathematical functions (`sin`)
* Efficient screen updating to avoid flickering
* Basics of waveform visualization (grid + plotting)

---

##  Hardware Used

* STM32F103C8T6 (Blue Pill)
* ST7789 TFT Display (160x128)
* Jumper wires

---

##  Features Implemented

*  Sine wave generation using math library
*  Grid display (like oscilloscope background)
*  Center reference line
*  Smooth waveform animation
*  Flicker reduction using pixel overwrite method

---

##  How It Works

1. A sine wave is generated using:

   * Angle calculation
   * `sinf()` function
2. Values are mapped to screen coordinates
3. Each frame:

   * Old wave pixels are erased
   * New wave is drawn
4. Grid provides reference for visualization

---

## ST7789 TFT Display Connections

| TFT Pin    | STM32 Pin | Description           |
| ---------- | --------- | --------------------- |
| VCC        | 3.3V      | Power supply          |
| GND        | GND       | Ground                |
| SCL (SCK)  | PA5       | SPI Clock             |
| SDA (MOSI) | PA7       | SPI Data              |
| RES (RST)  | PA0       | Reset pin             |
| DC (A0)    | PA1       | Data/Command control  |
| CS         | PA2       | Chip Select           |
| BLK        | 3.3V      | Backlight (always ON) |

---

## STM32 Peripheral Configuration

## SPI1 Configuration

Mode: Master
Direction: 2 Lines (Full Duplex)
Data Size: 8-bit
Clock Polarity: Low
Clock Phase: 1st Edge
Baud Rate Prescaler: 8
First Bit: MSB

---

## DMA Configuration
DMA1 Channel3 used for SPI TX
Enables faster display updates

---

## Notes
SPI is used to communicate with the TFT display
GPIO pins (PA0, PA1, PA2) are used for control signals (RST, DC, CS)
DMA helps improve performance for graphics rendering

---
##  Output

Displays a moving sine wave on the TFT screen similar to an oscilloscope display.
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/1207aecd-08d8-4fa3-872c-f4eab0dc7ea4" />
<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/66781109-d49b-40a0-a8d6-6dcfdaa6abaa" />

---

##  Future Improvements

* Add real signal input using ADC
* Implement multiple waveforms (square, triangle)
* Add scaling (voltage/time)
* Improve drawing speed using DMA

---

##  Note

This project is a stepping stone toward building a **real-time digital oscilloscope**.

---

##  Author

Swapnali Rathod.
