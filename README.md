# ToDo list
## HW
- Connect the Antenna button
- Connect the Volume button
- Connect the High frequencies
- Connect the Low frequencies
- Connect the switches (On/Off, PU, GO, PO, OC, MF)

- Connect a Rotary Encoder with Push-Button
- Rotary potentiometer (generic)

## SW
- BLE
  - Wifi SSID
  - Wifi PWD
  - Source (FM or Web)
  - Frequency
  - URL
- Connect to WiFi
- WebRadios flow
- SI4703
- TEA5767

### Resources
[Radio Arduino Library](https://www.mathertel.de/Arduino/RadioLibrary.aspx)

# esp-idf-tea5767
TEA5767 FM Stereo Radio Driver for esp-idf.

I ported from [here](https://github.com/andykarpov/TEA5767).   

# Software requirements
ESP-IDF V4.4/V5.x.   
ESP-IDF V5.0 is required when using ESP32-C2.   
ESP-IDF V5.1 is required when using ESP32-C6.   

# Hardware requirements   
TEA5767 FM Stereo Radio Module.   
I bought this on AliExpress about $4.   

![tea5767-1](https://user-images.githubusercontent.com/6020549/146292319-adf96f9a-f076-4b4f-be9f-2a2928c0b92f.JPG)
![tea5767-2](https://user-images.githubusercontent.com/6020549/146292325-c70aaddb-6f61-45ca-8de3-42ba3f375876.JPG)

The module has a standard antenna, but if you want to use it in a room, you need a long antenna.   
With a long antenna, you can get more signals.   
I used an AC power cable as extended antena.   
![tea5767-3](https://user-images.githubusercontent.com/6020549/146294473-9b514cf8-ca94-49d8-a723-ec67185ec119.JPG)


# Installation
```
git clone https://github.com/nopnop2002/esp-idf-tea5767
cd esp-idf-tea5767
idf.py set-target {esp32/esp32s2/esp32s3/esp32c2/esp32c3/esp32c6}
idf.py menuconfig
idf.py flash
```

# Configuration   

![config-top](https://user-images.githubusercontent.com/6020549/146292879-4be4bc9b-6a2e-4cb9-b0a8-bdad5fae8615.jpg)
![config-tea5767](https://user-images.githubusercontent.com/6020549/146292884-e29e45a4-4f99-4314-bb20-4f03bacbe2f7.jpg)

- CONFIG_SCL_GPIO   
 GPIO number(IOxx) to SCL.
- CONFIG_SDA_GPIO   
 GPIO number(IOxx) to SDA.
- CONFIG_FM_BAND   
 In US/EU it ranges from 87.5 MHz to 108 MHz.   
 In Japan it ranges from 76 MHz to 91 MHz.   
 Used when wrapping in a search.   

# Wiring

|TEA5767||ESP32|ESP32-S2/S3|ESP32-C2/C3/C6||
|:-:|:-:|:-:|:-:|:-:|:-:|
|SCL|--|GPIO22|GPIO4|GPIO6|(*1)|
|SDA|--|GPIO21|GPIO3|GPIO5|(*1)|
|GND|--|GND|GND|GND||
|VCC|--|3.3V|3.3V|3.3V|(*2)|

(*1)   
You can change it to any pin using menuconfig.   
__But it may not work with other GPIOs.__

(*2)   
The PCB marking is +5V, but it works at 3.3V.   


# API
Refer to tea5767.h.   

# How to use   

- Search radio station   
 Press the + key to search for radio stations upwards.   
 Press the - key to search for radio stations downwards.   

- Preset radio station   
 Press the * key to record the current radio station in NVS.   
 At boot time, it read from NVS and set to the current Radio station.   

- Change frequence   
 Press the D key to decrease the frequence by -1.0Mhz.   
 Press the U key to increase the frequence by +1.0Mhz.   
 Press the d key to decrease the frequence by -0.1Mhz.   
 Press the u key to increase the frequence by +0.1Mhz.   

- Clear preset   
 ```idf.py erase-flash```   


# Reference   
https://github.com/nopnop2002/esp-idf-fm-radio

