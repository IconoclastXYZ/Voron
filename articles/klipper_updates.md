# Simplying MCU klipper updates
How to update klipper on the different MCUs in the system after updating it on the Raspi

## Learning points...
- I started the CANBus journey with the WaveShare RS485-CAN-HAT and although there are comments to the contrary it worked well and was stable, with a bus speed of 250000 bps (baud)
- I needed to change away from the WaveShare as I wanted to install the KlipperScreen mod, and the Waveshare board neatly part covers the screen connector on the RasPi
- Rather than have _yet another controller board_ I opted to do the CANBus over USB solution on the Octopus 1.1. It is a bit of a fiddle to setup because:
1. you need an RJ11 connector - found an old telephone cable and butchered it
2. you need canboot loaded on the Octopus - then Klipper is loaded over the top of it - done

- Problem comes when you want to update Klipper as it cannot be done directly over serial as before since the Octopus is not directly connected to the RasPi, but rather through CANBus. Therefore a *bunch* of solutions are proposed on the internet to work around this, double tap the reset button, suspend Klipper startup _just_ as the RasPi starts, etc. None worked reliably for me. In the end, lift up the printer, connect the jumper across the boot pins, restart the printer, reinstall CanBoot, then reinstall Klipper. Yuck!
- After doing that a few times, then having the EBB no longer be found it was too much, so off to BTT U2C school. This little controller is cheap, but the current version has PROBLEMS and I eventually found this guide from [Eric Zimmerman](https://github.com/EricZimmerman/VoronTools/blob/main/EBB_CAN.md) on how to perform the necessary miracles and make it work.
- Of course it hard coded firmware from BTT has a bus speed of 1000000, so a few long USB cables later, the EBB36 is reflashed with CanBoot and Klipper and everything is talking again.

## Update the controller board - when using the WaveShare RS485-CAN-HAT or BTT U2C board
<img src="/images/KlipperSetup-Octopus.png" width="800">

```
cd ~/klipper/
make clean KCONFIG_CONFIG=config.octopus
make menuconfig KCONFIG_CONFIG=config.octopus
make KCONFIG_CONFIG=config.octopus

sudo service klipper stop
make flash FLASH_DEVICE=/dev/serial/by-id/usb-Klipper_stm32f446xx_430011000650535556323420-if00
sudo service klipper start

#or if it fails then use
make flash FLASH_DEVICE=/dev/serial/by-id/usb-CanBoot_stm32f446xx_430011000650535556323420-if00
```

## Then the BTT EBB CANBus Board - directly with WaveShare or U2C
## Be sure to choose speed of 1000000 not 250000!!!
<img src="/images/KlipperSetup-EBB36.png" width="800">

- making sure you choose the right version as the CANBus pins have changed between [versions](https://github.com/bigtreetech/EBB)
- after setting it up with [CANBoot](https://github.com/Arksine/CanBoot), explained [here](https://www.youtube.com/watch?v=_FELCN8CbWA):
```
cd ~/klipper/
make clean KCONFIG_CONFIG=config.ebb
make menuconfig KCONFIG_CONFIG=config.ebb
make KCONFIG_CONFIG=config.ebb

mv ~/klipper/out/klipper.bin ~/firmware/EBB_1.2_klipper.bin

cd ~/CanBoot/scripts
python3 flash_can.py -i can0 -f ~/firmware/EBB_1.2_klipper.bin -u d3e7f0c00d1a
```
- Just remember that sometimes the Pi will not find the MCU after a service stop and new make, requiring a power cycle of the whole system - much time wasted figuring this one out!
