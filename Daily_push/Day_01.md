# Bitwise Operators
In Embedded sytems a variable is a row of switches
- Bitwise operations are used to manipulate individual bits of a number
- example ` uint8_t reg = 13`, here 13 = 00001101, where each bit is a switch"
- Each switch controls hardware, i.e 1 = ON, 0 = OFF
- example `bit 1 = LED` in Stm32 uc

### Important note - what each bit does changes depending on the micro-controller so it is important to be able to read the datasheet/manual of that micro-controller

## | OR 
- It is used to set a bit
- `reg |= (1<<5)` - This shifts the value 1 to the 5th position, `00000000` becomes `00100000`
- If `bit 5 = LED perihperal` - We just turned on the LED
- `reg = (1<<5)` - don't do this it will clear all other bits, i.e if any other peripheral was ON (bit was 1) it will be turned OFF (bit becomes 0)

## & AND
- It is used to check bits
- `if (reg & (1<<3)` - This will check if the bit is 1 in reg at position 3, if it is certain commands will be executed

## ~ NOT
- It is used to switch bits, 1 -> 0 and 0 -> 1
- If used together with `&`, it can clear bits [make it 0]
- `reg &= ~(1<<5)` - The value of the bit at position 5 becomes 0 [OFF], so only the peripheral linked to that bit is turned OFF

## Left and Right shift
- Left shift is used to mask a bit [change the bit at the specified position without changing the bit at the other positiont]
- Right shift is used to extract value [if a bit has say sensor values, then right shift can be used to changes the postion to make so that value is extractable]

## Commonly used Bitwise operations
- Set bit - `|=`
- Clear bit - `&= ~`
- Toggle bit - `^=`
- Check bit - `if( register & bit_position)`

## Register ??
- So a register can store either 0 or 1
- Say there is a 8-bit register, It might imply that there are 8 different operations that this register can turn ON/OFF
- To access a register in a peripheral we check the Datasheet/Manual to use something like `RCC->AHB1ENR`
      - It means access the `AHB!ENR` register in the `RCC` peripheral

## Bit Field
- Sometimes to select a mode or operation we tie it to a combination of bits insteas of a single bit
- That is we use `11 or 10` instead of just ` 1` or `0`
- Going forward with our examples `10 = 2` so i can use `reg |= (2<<4)` so now bit 5 and 4 are 1 and 0 respectively 

