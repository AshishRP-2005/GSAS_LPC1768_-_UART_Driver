# Day 3

## `volatile` Keyword
- The compiler is a clever machine, it always optimizes the code to make it faster and more efficient to use
- But it makes a mistake of assuming that a value of a variable will only change in the code flow and never outside it, mapping it to a register and not looking into that variable again
- That is not true, the value of the variable can be changes by the hardware/CPU/interrupt or any external prcoess, which the compiler will not catch because of its assumption
- This is where the `volatile` keyword comes in it basically tells the compiles that the value of this variable MAY change outside of normal code flow so don't fix it to a register 
- Example - `volatile unsigned int stat` - the stat variable will not be assigned a fixed memory and will be checked into during each iteration
