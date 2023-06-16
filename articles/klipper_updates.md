# Simplying MCU klipper updates
How to update klipper on the different MCUs in the system after updating it on the Raspi

## Update the controller board
```
cd ~/klipper/
make clean KCONFIG_CONFIG=config.octopus
make menuconfig KCONFIG_CONFIG=config.octopus
make KCONFIG_CONFIG=config.octopus

sudo service klipper stop
make flash FLASH_DEVICE=/dev/serial/by-id/usb-Klipper_stm32f446xx_430011000650535556323420-if00
sudo service klipper start
```
## Then the BTT EBB CANBus Board 
<img src="/images/KlipperSetup-EBB36.png" width="800">

- making sure you choose the right version as the CANBus pins have changed between [versions](https://github.com/bigtreetech/EBB)
- after setting it up with [CANBoot](https://github.com/Arksine/CanBoot), explained [here](https://www.youtube.com/watch?v=_FELCN8CbWA):
```
cd ~/klipper/
make clean KCONFIG_CONFIG=config.ebb
make menuconfig KCONFIG_CONFIG=config.ebb
make KCONFIG_CONFIG=config.ebb
  
cd ~/klipper/lib/canboot
python3 flash_can.py -i can0 -f ~/klipper/out/klipper.bin -u d3e7f0c00d1a
```
- Just remember that sometimes the Pi will not find the MCU after a service stop and new make, requiring a power cycle of the whole system - much time wasted figuring this one out!
