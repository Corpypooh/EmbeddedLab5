#include <msp430.h>
int main(void)
{
    WDTCTL = WDT_ADLY_250;    // WDT 250ms, SMCLK, interval timer
    P6OUT &= ~BIT6;           // Green LED
    P6DIR |= BIT6;            // Green LED
    PM5CTL0 &= ~LOCKLPM5;     // Stops low power mode
    SFRIE1 |= WDTIE;
    _enable_interrupts();
    while (1);
}

    #pragma vector=WDT_VECTOR
__interrupt void wdtled(void)
{
    P6OUT^=BIT6;      // Green LED activate after interrupt
}
