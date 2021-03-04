# mrk-non-deflault-Arduino-i2c-pins


Welcome to the mrk-non-deflault-Arduino-i2c-pins wiki! Here is a general way to use non arduino default i2c pins on the mrk zero. therefor you have to know which pins do use which sercom in my case i give an example with sercom 3 sdapin 0 sclpin1

1.than you need to import #include "wiring_private.h"

2.declare vars like uint8_t SDA1 = 0; uint8_t SCL1 = 1; TwoWire I2Cone = TwoWire(&sercom3, SDA1, SCL1);

3.add an begin fkt and callit after serial.begin in voiud setup. void AS5600::Begin() { I2Cone.begin(); // SDA pin 21, SCL pin 22 TTGO TQ pinPeripheral(0, PIO_SERCOM); //Assign SDA function to pin 0 pinPeripheral(1, PIO_SERCOM); }

4.replace all "Wire" with "I2Cone"
