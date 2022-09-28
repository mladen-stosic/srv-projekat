# srv-projekat
Code Composer Studio Project for Real-time Systems course

Written in C, utilizing FreeRTOS 

### Project task:
Start acquisition from A0 and A1 ADC channels every 1000ms using xTaskTimer task that uses vTaskDelayUntil function. 
Implement ADC delayed interrupt proccessing, so that xTask1 waits for Queue that's filled from ISR.
Queue message should contain number of read channel and 12-bit read from ADC.
xTask1 should calculate average value of last 16 read values from each channel seperately, and send it to xTask2 and xTask3 by Direct-to-task notification used in mailbox mode.
Values are to be sent with 'overwrite' attribute. Tasks xTask2 & xTask3 shouldn't be blocked after reading value from mailbox. When ASCII characters '2' & '3' are received over UART tasks xTask2 and xTask3, respectively, should read their respective mailboxes and display them on multiplexed 2 digit 7-segment displays (Values should be scaled so that displayed value fits [00-FF]). Access to multiplexed LED display is guarded by gatekeeper task xTaskLED that is accessed only by it's own Queue.

### Hardware used:
MSP430F5529 development board by Texas Instruments \
Add-on board with potentiometers connected to Vcc and ground, the 3rd lead connected to MC ADC ports, buttons and 7-segment display, provided by faculty

