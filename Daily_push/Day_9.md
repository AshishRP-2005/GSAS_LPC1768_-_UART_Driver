# Day 9

- UART Hardware is like a mailbox system
- You see if your box is empty, put in a mail and wait for the carrier to take the mail from the box

## Format
- So Bits through UART are sent in a format
- Format implies, how many data bits, how many parity bits, Stop bits etc
- `8N1` is the most common UART format
    - It has 8 Data bits
    - No parity bits
    - 1 Stop bit

# Configuration
- Previously we had talked about PIN multiplexing
- We use `PINSEL` to select the function of the pin
- It is to make sure that the TX and RX pins are selcted out of the several available functions of the pins
- `PINSEL0` = UART, `P0.2->TXD0`, `P0.3->RXD0`
   
