# Project 2: UART Communication on PIC Microcontroller

## 🔹 Overview
This project demonstrates UART (Universal Asynchronous Receiver-Transmitter) communication on PIC16F877A using MPLAB X IDE and XC8 compiler.  
The microcontroller transmits and receives characters over serial communication, which can be monitored on a terminal (like PuTTY or Serial Monitor).

## 🔹 Hardware
- PIC16F877A (8-bit microcontroller)
- MPLAB X IDE + XC8 Compiler
- USB-to-Serial converter (if PC connection needed)
- Breadboard and jumper wires

## 🔹 Concepts Learned
- UART initialization
- Baud rate configuration
- Transmitting and receiving data via serial port

## 🔹 Circuit Diagram
Include your circuit diagram image here (save it as `circuit.png` in this folder).  

## 🔹 Code Snippet
```c
void UART_Init(long baudrate) {
    SPBRG = ((_XTAL_FREQ/16)/baudrate) - 1;
    TXSTAbits.TXEN = 1; // Enable transmission
    RCSTAbits.SPEN = 1; // Enable serial port
    RCSTAbits.CREN = 1; // Enable continuous receive
}

void UART_TxChar(char ch) {
    while(!TXSTAbits.TRMT);
    TXREG = ch;
}

