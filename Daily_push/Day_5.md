# Day 5
### Note - I had my internals so couldn't properly push for 1-2 days, so this isn't exactly day 5 but i am gonna let it slide

## Pin Multiplexing
- Each physical pin on the microcontroller has more then one peripheral connected to it
- Which means i can use the same pin to send as a GPIO or UART or SPI or any other peripheral
- Important to note you can't use peripherals simultaneously on a pin, it is serial only 1 peripheral at a time

## Why is this needed
- without pin multiplexing if we give each peripheral it's own pin then the microcontroller will be too large abd well... no longer be micro exactly
- There are other reasons as well like power constraints

## Advantage and Disadvantage
- This is very felxible allowing for saving space and time, trade off is there might be pin configuration issues and more debbugging

## How to do it?
- So pin multiplexing is done in 2 stages
    - Peripheral configuration - The internal peripheral is configured to recieve/transmit values after routing a physical pin to it
    - Routing - Assigning the physical pin to the internal peripheral by referring the datasheet
- Routing is done using `PINSEL`
- Configuring is done by referring the `DATASHEET`
