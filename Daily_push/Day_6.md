# Day 6

## GPIO
- General purpose input output pins
- They are used for simple and well general tasks like turning on a LED, or providing delays
- They are bascically, Configure peripheral, clear bit, set bit and toggle bit, Which is what most of embedded sytems will boil down to

## GPIO Architecture
- For the LPC1768, Some common code for Configuring peripheral and pins
  - `PINSEL` - Specifies what the Pin will do (pin multiplexing)
  - `FIODIR` - Selects whether a pin in input or output, selecting its direction ` 1 = OUTPUT, 0 = INPUT`
  - `FIOSET` - Set HIGH
  - `FIOCLR` - Set LOW
  - `FIOPIN` - Read pin state
      
