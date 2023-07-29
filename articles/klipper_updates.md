# Simplying MCU klipper updates
How to update klipper on the different MCUs in the system after updating it on the Raspi

## Update the controller board - when using the WaveShare RS485-CAN-HAT
<img src="/images/KlipperSetup-Octopus.png" width="800">

```
cd ~/klipper/
make clean KCONFIG_CONFIG=config.octopus
make menuconfig KCONFIG_CONFIG=config.octopus
make KCONFIG_CONFIG=config.octopus

sudo service klipper stop
make flash FLASH_DEVICE=/dev/serial/by-id/usb-Klipper_stm32f446xx_430011000650535556323420-if00
sudo service klipper start
```
## Update the controller board - when using CanBUS Bridging on the Octopus
<img src="/images/KlipperSetup-Octopus-CanBUS.png" width="800">

- Once in the CanBUS Bridge mode it cannot be directly flashed with new firmware
- The instructions [here](https://klipper.discourse.group/t/octopus-pro-canboot-can-bus-bridge/3734/21?page=2) and [here](https://github.com/akhamar/voron_canbus_octopus_sb2040#update-klipper-on-the-octopus) imply that you can trigger it back into CanBoot mode by trying:
```
python3 flash_can.py -i can0 -u c4881dcf2900 -f ~/firmware/octopus_1.1_klipper.bin
```
- Then flash using the sequence below, otherwise use the info [here](https://github.com/akhamar/voron_canbus_octopus_sb2040#flashing-images) to reflash CanBoot onto the Octopus - basically switch the DFU jumper and run
```
sudo dfu-util -a 0 -D ~/firmware/octopus_1.1_canboot.bin --dfuse-address 0x08000000:force:mass-erase:leave -d 0483:df11
```
- Either way, then you can flash the klipper firmware by serial
```
cd ~/klipper/
make clean
make menuconfig
make

mv ~/klipper/out/klipper.bin ~/firmware/octopus_1.1_klipper.bin

cd ~/CanBoot/scripts
python3 flash_can.py -f ~/firmware/octopus_1.1_klipper.bin -d /dev/serial/by-id/usb-CanBoot_stm32f446xx_430011000650535556323420-if00
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

mv ~/klipper/out/klipper.bin ~/firmware/EBB_1.2_klipper.bin

cd ~/CanBoot/scripts
python3 flash_can.py -i can0 -f ~/firmware/EBB_1.2_klipper.bin -u d3e7f0c00d1a
```
- Just remember that sometimes the Pi will not find the MCU after a service stop and new make, requiring a power cycle of the whole system - much time wasted figuring this one out!
