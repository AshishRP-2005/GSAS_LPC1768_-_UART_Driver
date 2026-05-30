# Day 8
## What is UART?
- Universal Asynchronous Reciever/Transmitter
- It is a communication protocol
- Data is sent and recieved serially through wires
- `0100001`
    - exist as a byte in the parallel world of the computer
    - when sent through UART
    - `start bit = 0`
    - `data bits = 1->0->0->0->0->1->0` is sent on bit at a time
    - `stop bit = 1`
- UART allows and is used widely for communcation between different peripherals, microcontrollers, PC etc
- For communication to take place both devices must agree upon
    - baud rate
    - stop bits
    - parity
    - data size

## TX and RX pins
- TX is the transmitter pin it sends out data
- RX is the reciever pin it recieves data
- TX of one device connects to RX of another device and vice versa
- TX of one device can't connect to TX of another device won't work

## Baud rate
- This is basically transmission speed
- Like a common value is `9600`, it means 9600 bits/second is transferred
