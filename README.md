
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
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


```
### (ii) Serial Port to Transfer a Message

```
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



```

### OUTPUT:
<img width="791" height="416" alt="image" src="https://github.com/user-attachments/assets/35c5b5cc-d30e-48e1-9a39-fb3527e437c2" />

<img width="776" height="452" alt="image" src="https://github.com/user-attachments/assets/06b03b74-c682-4e0b-8dfc-f6f55588299e" />




### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
