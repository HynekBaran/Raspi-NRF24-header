# Raspi-NRF24-header
Raspberry Pi NRF24L01 header (incl. 5V to 3V3 voltage regulator and additional SPI header)

This PCB is modified version of
https://www.openhardware.io/view/17/Raspberry-Pi2-GPIO-interface-for-NRF24L01.

####Usage with MySensors
May be used as MySensors.org gateway, see
https://github.com/mysensors/Raspberry
for details.

#####Installation of MySensor's gateway
``` bash
 # NRF24 Libraries
 apt install git make g++ rsyslog
 git clone "https://github.com/TMRh20/RF24.git"
 cd RF24/
 make all
 cd ..
 # MySensor gateway for Raspberry Pi
 git clone "https://github.com/mysensors/Raspberry.git"
 cd Raspberry/
 make all
 sudo make install
 sudo make enable-gwserial
 ```
 
#####Usage
 
 Your gateway as available as `/dev/ttyMySensorsGateway`

 If accesing by some software controller, it has to have an access rights to above device.
 E.g., when using FHEM controller, allow it to access /dev/ttyMySensorsGateway by
``` bash
 usermod -a -G tty fhem
 ```
####PWR_SEL jumper (must be shorted correctly)
Select power source by connecting a jumper to the proper pair of pins:
```
Short 3V3_NRF <---> 3V3PI  if using Raspberry's internal 3V3 (take care!)
Short 3V3_NRF <---> 3V3EXT if assembled LD117 regulator 
                              and feed the device via EXT_PWR_IN 5V pin (e. g. connected to Raspi 5V)
```
Without a proper short/jumper described above, radio is not powered!

####PWR_OUT1, PWR_OUT2 headers (optional)
PWR_OUT1, PWR_OUT2 headers may be used to feed any optional external 3.3 V device

<a href="https://oshpark.com/shared_projects/ncBBwenI"><img src="https://a800d827b6de8403a51e-6ffc2e718631809086ea40332b2055f7.ssl.cf1.rackcdn.com/assets/badge-5b7ec47045b78aef6eb9d83b3bac6b1920de805e9a0c227658eac6e19a045b9c.png" alt="Order from OSH Park"></img></a>
