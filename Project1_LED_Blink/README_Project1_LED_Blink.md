# Project 1: LED Blink on PIC Microcontroller

## 🔹 Overview
This project demonstrates a simple LED blink program on PIC16F877A using MPLAB X IDE and XC8 compiler.  
The LED toggles every 500ms using Timer0.

## 🔹 Hardware
- PIC16F877A (8-bit microcontroller)
- MPLAB X IDE + XC8 Compiler
- LED + resistor + breadboard

## 🔹 Concepts Learned
- GPIO pin configuration
- Timer interrupts
- Delay generation in embedded systems

## 🔹 Circuit Diagram
Include your circuit diagram image here (save it as `circuit.png` in this folder).  

## 🔹 Code Snippet
```c
void __interrupt() ISR() {
    if (T0IF) {
        LATBbits.LATB0 ^= 1;  // Toggle LED
        T0IF = 0;
    }
}
```

## 🔹 Output
The LED blinks with approximately 1Hz frequency.
