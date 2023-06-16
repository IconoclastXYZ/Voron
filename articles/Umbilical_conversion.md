# Converting to an Umbilicus rather than drag chains

## What is needed to change
- Swap to CanBUS
- Move x-endstop to toolhead
- Move y-endstop to A-motor mount
- Make end mounts for the umbilicus

## CanBUS hardware
- Need a controller board to drive from the Raspi - [WaveShare CanBus adaptor](https://learn.sb-components.co.uk/RS485-CAN-HAT)
-- Now people recommend the BTT U2C board instead, explained [here](https://wiki.kb-3d.com/home/canbus_guide)

- CAN Bus board from [BigTreeTech](https://www.aliexpress.com/item/1005004243374113.html) with the [GitHub and manual](https://github.com/bigtreetech/EBB/)
-- Ended up using the BTT EBB36 1.2 with a [canbus mount](https://github.com/KayosMaker/CANboard_Mounts)
-- With a great introduction on how to flash the firmware and wire it up [here](https://wiki.kb-3d.com/en/home/btt/voron/BTT_EBB36)
- Final wiring for the EBB36 board
<img src="/images/EBB36 Voron wiring 2022-12-29 15_43_52.png" width="600">

- Add to /boot/config.txt (note the need for the \[all\] otherwise it can slip under Pi2, Pi3 or Pi4 and not work
```
[all]
dtparam=spi=on
dtoverlay=mcp2515-can0,oscillator=12000000,interrupt=25,spimaxfrequency=2000000
```
- With more info on how to setup CAN Bus [here](https://www.klipper3d.org/CANBUS.html)

## Moving x-endstop
- Built-in mount point on the new Stealthburner design

## Moving y-endstop
- [No need to reprint the A-motor mount](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Minsekt/Rear_Umbilical/Y_Endstop_Relocation)
- [Alt - no need to reprint the A-motor mount](https://github.com/RepRapster/Voron2.4-Rear-Gantry-Y-Endstop-Mount) - also reduces the offset required
- [Reprint of A-motor mount required](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/hartk1213/Voron2.4_Y_Endstop_Relocation)

## Umbilicus mount for toolhead
- [Designed for Stealthburner](https://github.com/majarspeed/Misc-Voron/tree/main/StealthBurner%20Umbilical%20cover)

## Umbilicus mount for A-motor
- [No need to reprint the mount](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Minsekt/Rear_Umbilical)
- And a cleaner one [here](https://www.printables.com/en/model/412460-voron-24-a-drive-pg7-umbilical-mount-with-cable-cu)

## Cable end protectors
- [PG7 cable glands at each end](https://www.amazon.com.au/gp/product/B08K8FB4KV/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&th=1)
- Mod the end mounts to include a thread for the cable gland (1/2-20 UNF thread)

## Moved the Z chain to be underslung, saving space out the back
- [Various versions for canbus](https://www.printables.com/model/279739-voron-can-bus-z-chain-move/files)
