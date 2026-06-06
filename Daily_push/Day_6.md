# Day 6

## GPIO
- General purpose input output pins
- They are used for simple and well general tasks like turning on a LED, or providing delays
- They are bascically, Configure peripheral, clear bit, set bit and toggle bit, Which is what most of embedded sytems will boil down to

## GPIO Architecture
- For the LPC1768, Some common code for Configuring peripheral and pins
  - `PINSEL` - Specifies what the Pin will do (pin multiplexing)
  - `FIODIR` - Selects whether a pin in input or output, selecting its direction ` 1 = OUTPUT, 0 = INPUT`
  - `FIOSET` - Set HIGH `when 1 = HIGH`
  - `FIOCLR` - Set LOW `when 1 = LOW`
  - `FIOPIN` - Read pin state

## Question 
To Set a BIT or Clear a BIT, I can use |= and &= ~() respectively, So why is there a need for different SET and CLR codes?
- Apparently it is to increase speed and make sure that the accidently some other pin is not Set or Cleared

## Reusable Driver Code
- Instead of writing a line like `FIOSET |= (1<<22)` everywhere in the code. We can write
- `void LED(void) { FIOSET |= (1<<22)}` Once at the start of the Program and just use `LED()` wherever it is required
- Better yet `void LED(uint32_t pin) { FIOSET |= (1<<pin)}` - this will create a reusable code where i can use it for any PIN
