# **Project#1 Heartbeat LED**
By Alex Deadmond

## **Project Description:**
In this project two heartbeat LEDs were implemented on the MSP430FR2355. 
The LEDs blink at 0.5 Hz, or one second off and one second on.
One LED was blinked using a delay loop, and the other using an interrupt.


### **Delay Loop Flowchart**
![The delay loop flowchart](/docs/assets/Delay_Loop_Flowchart.png)

In order to get the timing correct I found that the microcontroller was using a clock that operated at 228.18 kHz.
I implemented an inside and outside loop that, together, counted down from 228180. This way it would toggle the LED every second effectively making a 0.5 Hz heartbeat LED.



### **Interrupt Flowchart
![The interrupt flowchart](/docs/assets/Interrupt_Flowchart.png)

To get the timing correct I first looked at the clock I used for the timer interrupt. I used SMCLK which runs at 32.786 kHz. This means that if I initialized my CCR0 with 32786 I could make it so that the LED gets toggled every second. This way a 0.5 Hz heartbeat LED could be implemented with an interrupt. 
