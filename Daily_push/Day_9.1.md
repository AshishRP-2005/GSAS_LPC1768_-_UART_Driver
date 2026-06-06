# Day 10

## C code for UART Driver

1. Header file
```
   #ifndef uart_h
#define uart_h

void init(void);
void TXchar(char c);
void TXstring(char *str);
void RX(void);

#endif
```

2. UART FUNCTION FILE
```
#include<LPC17xx.h>
#include "uart.h"

void init(void){
	LPC_PINCON->PINSEL0 &= ~((3<<4)|(3<<6));
	LPC_PINCON->PINSEL0 |= ((3<<4)|(3<<6));

	LPC_UART0->LCR = 0x83;

	LPC_UART0->DLL = 163;
	LPC_UART0->DLM = 0;

	LPC_UART0->LCR = 0x03;
}

void TXchar( char c)
{
	while(!(LPC_UART0->LSR & (1<<5)));
	LPC_UART0->THR = c;
}

void TXstring(char *str)
{
	while(*str)
	{
		TXchar(*str++)
	}
}

char RX(void)
{
	while(!(LPC_UART0->LSR & (1<<0)));
	return LPC_UART0->RBR;
}
```

3. Main File
```
#include <LPC17xx.h>
#include "uart.h"

int main(void)
{
	char ch;
	init();
	TXstring("UART Driver is Ready \n");
	
	while(1)
	{
		ch = RX();
		TXchar(ch);
	}
}
```

