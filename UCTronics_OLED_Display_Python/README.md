# UCTRONICS OLED Display - Python Version

Enables the the OLED display for UCTRONICS Pi 4 Rack Module.

### NB, This addon will take some time to initially load as it has to build some python libraries. 


This addon includes a splash screen that will show you the current version of the Core OS, and HA, and will be presented with an astricx if either require an upgrade. You are also able to set the duration of the slide rotation, and what slides you wish to present.


## First Step  - Enable i2c
### Option 1  - Official
[Official Documentation](https://www.home-assistant.io/common-tasks/os#enable-i2c-with-an-sd-card-reader) 

### Options 2 - Best Choise
This addon from Adam Outler, [GitHub adamoutler](https://github.com/adamoutler/HassOSConfigurator/tree/main/Pi4EnableI2C) to first enable the I2C interface, you will need to reboot twice as per his documentation. After I2C is enabled then you wil be able to use this. 


## Second Step - Enable this Addon.
1. Start the Addon
2. Check the "Log" and see if there are any errors.
3. Your OLED should be displaying.
