# Raspi-NRF24-header
Raspberry Pi NRF24L01 header (incl. 5V to 3V3 voltage regulator and additional SPI header)

Modified version of
https://www.openhardware.io/view/17/Raspberry-Pi2-GPIO-interface-for-NRF24L01

PWR_SEL jumper selects power source:
Short 3V3_NRF --- 3V3PI  if using Raspberry's internal 3V3 (take care!)
Short 3V3_NRF --- 3V3EXT if assembled LD117 regulator and feed it via EXT_PWR_IN 5V pin (e. g. connected to Raspi 5V)

PWR_OUT1, PWR_OUT2 headers may be used ro feed any external 3.3 V device
