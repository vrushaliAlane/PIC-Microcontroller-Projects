

## 📘 Project3: ADC Temperature Sensor

```markdown
# Project 3: ADC Temperature Sensor on PIC Microcontroller

## 🔹 Overview
This project demonstrates reading analog data from a temperature sensor (LM35) using the ADC module of PIC16F877A.  
The digital value is converted and displayed via UART/Serial Monitor.

## 🔹 Hardware
- PIC16F877A (8-bit microcontroller)
- MPLAB X IDE + XC8 Compiler
- LM35 Temperature Sensor
- USB-to-Serial converter (for monitoring)
- Breadboard and jumper wires

## 🔹 Concepts Learned
- ADC configuration and initialization
- Analog-to-digital conversion
- Sending sensor data to PC via UART

## 🔹 Circuit Diagram
Include your circuit diagram image here (save it as `circuit.png` in this folder).  

## 🔹 Code Snippet
```c
unsigned int ADC_Read(unsigned char channel) {
    ADCON0 = (channel<<3);  // Select ADC channel
    ADCON0 |= 0x01;         // Turn on ADC
    __delay_ms(2);          // Acquisition time
    GO_nDONE = 1;           // Start conversion
    while(GO_nDONE);
    return ((ADRESH<<8)+ADRESL);
}
