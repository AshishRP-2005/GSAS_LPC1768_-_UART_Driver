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
    - data bits
