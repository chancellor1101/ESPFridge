# ESPFridge
The goal of this project to to overhaul a thermoeletric fridge, like the ones you can purchase from Love's Travel Centers, or your [local Walmart](https://www.walmart.com/ip/Coleman-40-Quart-PowerChill-Thermoelectric-Cooler-with-Power-Cord/21156022). The design is to be able to monitor the temperature inside of the cooler, control fan speeds and power to the thermoeletric pads. Notifications should be given to a paired smart phone.

# Hardware taken into consideration
* [ESP32](https://www.amazon.com/HiLetgo-Development-Display-ESP-WROOM-32-WiFi-BT/dp/B072HBW53G/ref=sr_1_19?keywords=ESP32&qid=1558017681&s=gateway&sr=8-19)
* [Thermoeletric Cooler](https://www.walmart.com/ip/Coleman-40-Quart-PowerChill-Thermoelectric-Cooler-with-Power-Cord/21156022)
* [Temperature Probe](https://www.amazon.com/Gikfun-DS18B20-Temperature-Waterproof-EK1083x3/dp/B012C597T0/ref=sr_1_1_sspa?keywords=Temperature+Probe+arduino&qid=1558017847&s=gateway&sr=8-1-spons&psc=1)
* [Relay](https://www.amazon.com/XCSOURCE-Channel-Optocoupler-Arduino-TE213/dp/B00ZR3B252/ref=sr_1_3?keywords=3v+coil+12V+relay&qid=1558018004&s=gateway&sr=8-3)
* [Mosfet](https://www.amazon.com/CJRSLRB-IRF520-MOSFET-Driver-Arduino/dp/B077V57YLN/ref=sr_1_8?crid=1RVVC0GJEJDSE&keywords=mosfet+breakout+board&qid=1558018215&s=gateway&sprefix=mosfet+breakout%2Caps%2C302&sr=8-8)

# Calculations
## Battery Size Calculation
For the battery size you need to take into consideration, how cold you would like to get down to (Typically stock is around 20F below AMBIENT temperatures). Take into account the power consumption for each fan the unit has. (Mine has 2). Generally for the outer fan, a power consumption of 0.5A. So my calculation would be as follows:
***120MM Outside fan: 12V * .5 = 6W***
***80MM Inside fan: 12V * .66 = 8W (7.92W)***
So taking the 6W, it would require 6Wh of battery power to run the fan for 1 hour. And Likewise for the inside fan, 8Wh. That means we need a combined total of 14Wh to run both fans.
As for the thermoelectric pads, [A quick startpage search](https://browse.startpage.com/do/show_picture.pl?l=english&rais=1&oiu=https%3A%2F%2Fsc01.alicdn.com%2Fkf%2FHTB1Q.3YLXXXXXXaapXXq6xXFXXXz%2FTEC-12706-12v-6A-40-40mm-66W.jpg&sp=a53b2f7043fc4c2f360fc13746530162&t=default) shows that these modules use approximately 7A.

### Final Calculations:
* Outside Fan 6W (0.5A)
* Inside Fan 8W (0.54A)
* Thermoelectric Pad 7A
* Total Requirement 8.04Ah
