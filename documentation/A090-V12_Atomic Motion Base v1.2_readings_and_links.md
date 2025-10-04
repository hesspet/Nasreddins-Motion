# Specifications



|                Specification                |                          Parameter                           |
| :-----------------------------------------: | :----------------------------------------------------------: |
|                     MCU                     |                        STM32F030F4P6                         |
|               DC Motor Driver               |                            RZ7899                            |
|            Power Detection Chip             |                            INA226                            |
|          Charging/Discharging Chip          |                           ETA9740                            |
|           Battery Protection Chip           |                            DW01-A                            |
|    Charging/Discharging Cut-off Voltage     | Charge Cut-off Voltage 4.14V / Discharge Cut-off Voltage 2.5V |
|             Overload Protection             |                            5V@5A                             |
|          Removable Lithium Battery          |                         18350@900mAh                         |
|         Motor Interface PIN Spacing         |                            2.54mm                            |
|         Full Load Steering Current          |                              3A                              |
| Single Channel Motor Peak Operating Current |                              1A                              |
| Single Channel Servo Peak Operating Current |                             0.4A                             |
|         Standby Current (Switch On)         |                       DC4.04V@40.97uA                        |
|              Charging Current               |                         DC 5V@1.18A                          |
|            Operating Temperature            |                           0 ~ 40°C                           |
|                Product Size                 |                     75.4 x 24.0 x 20.7mm                     |
|               Product Weight                |                  41.0g (Including Battery)                   |
|                Package Size                 |                     79.0 x 31.0 x 26.0mm                     |
|                Gross Weight                 |                            45.3g                             |



# Pin Map



|   PIN   | LEFT | RIGHT | PIN  |
| :-----: | :--: | :---: | :--: |
|         |      |   1   | 3V3  |
| I2C_SCL |  2   |   3   |      |
| I2C_SDA |  4   |   5   |      |
|   5V    |  6   |   7   |      |
|   GND   |  8   |   9   |      |



# STM32

| STM32F030F4P6 | PA10 | PA9  | PA4  | PB1  | PA6  | PA7  |  PA0   |  PA1   |  PA2   |  PA3   |
| :-----------: | :--: | :--: | :--: | :--: | :--: | :--: | :----: | :----: | :----: | :----: |
|      I2C      | SDA  | SCL  |      |      |      |      |        |        |        |        |
|   DC Motor    |      |      | M1F  | M1R  | M2F  | M2R  |        |        |        |        |
|     Servo     |      |      |      |      |      |      | Servo3 | Servo1 | Servo4 | Servo2 |



