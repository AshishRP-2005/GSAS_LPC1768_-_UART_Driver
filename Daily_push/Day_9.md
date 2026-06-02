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
This means to Configure pins, set baud rate, set format etc
- Previously we had talked about PIN multiplexing
- We use `PINSEL` to select the function of the pin
- It is to make sure that the TX and RX pins are selcted out of the several available functions of the pins
- `PINSEL0` = UART, `P0.2->TXD0`, `P0.3->RXD0`

# DLAB
- So DLAB is a lock, basically it will unlock functions of UART for me and after using it i will lock it again
- `U0LCR |= (1<<7)` unlocks
      - `U0DLL`
      - `UODLM`
      - I think they are used in baud rate setting
- `U0LCR &= ~(1<<7)`

# Important and comman UART commands
- `U0THR`
      - Transmit holding register
      - It holds the Data that is ready to be transmitted
      - `U0THR = 'A'` - Sends ASCII value of A
- `U0LSR`
    - Line status register
    - Tells you whether UART is ready
    - Used to check if the Register empty or not
    - Status of register
- `U0LCR`
    - Line Control Register
    - This gives access to control of stop bits, start bits, parity bits, baud rate (through DLAB)
  
