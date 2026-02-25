
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character
#include <reg51.h>

void main(void)
{
    TMOD = 0x20;
    TH1  = 0xFA;
    SCON = 0x50;
    TR1  = 1;

    SBUF = 'A';

    while(TI == 0);
    TI = 0;

    while(1);
}

### (ii) Serial Port to Transfer a Message
#include <reg51.h>
void main(void)
{
    unsigned char msg[] = "VETRI";
    unsigned char i;
    TMOD = 0x20;
    TH1  = 0xFA;
    SCON = 0x50;
    TR1  = 1;

    for(i = 0; msg[i] != '\0'; i++)
    {
        SBUF = msg[i];
        while(TI == 0);
        TI = 0;
    }

    while(1);
}

### OUTPUT:
<img width="774" height="382" alt="image" src="https://github.com/user-attachments/assets/5eccb1d6-99d4-461f-aee5-e10c610ce6c3" />

<img width="764" height="444" alt="image" src="https://github.com/user-attachments/assets/4f7a3dd5-cf44-4f0e-92cd-9481a5e5af7d" />



### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
