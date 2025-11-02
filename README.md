
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character
```asm
ORG 00H
MOV TMOD, #20H
MOV TH1, #0FDH
MOV SCON, #50H
SETB TR1
MAIN_LOOP:
MOV SBUF, #'B'
WAIT_TI:
JNB TI, WAIT_TI
CLR TI
SJMP MAIN_LOOP
END


```
### (ii) Serial Port to Transfer a Message

```c
#include<reg51.h>
void main(void)
{
unsigned char msg[]="BHAVAN";
unsigned char i;
TMOD=0X20; //TIMER 1, MODE 2
TH1=0XFA;
SCON=0X50;
TR1=1;
for(i-0;i<=12;i++)
{
SBUF=msg[i];
while(TI==0);
TI=0;
}
while(1);
} 
```

### OUTPUT:
# (i)
<img width="457" height="352" alt="Screenshot 2025-11-02 COPY" src="https://github.com/user-attachments/assets/46635774-473f-4e2f-8e1a-ce90b6997378" />


# (ii)
<img width="563" height="457" alt="Screenshot 2025-11-02 160638" src="https://github.com/user-attachments/assets/3fec7e49-c415-4f1c-a130-636d45f78bdd" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
