# Voron
Build details, tips, tricks and traps for the 2.4 r1 - r2

<img src="/images/20220413_200053.jpg" width="300">

With a hotmesh from the finished printer

<img src="/images/2022-12-11%2015_27_04%20hot_mesh.png" width="600">

# Base build
## Formbot 3D kit - supplied to 2.4r1 specs but with
- hall effect XY endstops
- z endstop circuit board
- Phaetus Dragon HF hotend
- [BigTreeTech Octopus 1.1](https://www.biqu.equipment/products/bigtreetech-octopus-v1-1)
- Raspberry Pi 3B+ (1GB RAM)

There were a few traps for young players in the Formbot 3D build, outlined [here](https://github.com/IconoclastXYZ/Voron/blob/main/articles/formbot_build.md)

## What to print?
Third party (Etsy) printed parts in ASA to 2.4r1 with a few extra needed for the MGN12H rail

Turns out that they spontaneously printed the new (r2) din rail mounts for components, which is great

Quite a few other parts from r2 can be printed for r1 kits and only improve them, eg. z-axis and ab-axis idlers, all the skirts, all electronics mounts

## Things I wish I had known BEFORE starting to assemble the Voron
Lots of others build lists and hints exist, with my particular blind spots / learning points listed [here](https://github.com/IconoclastXYZ/Voron/blob/main/articles/build_lessons.md)
  
## Mods
<details>
  <summary>Physical</summary>
  
  - [Klicky mod](https://github.com/jlas1/Klicky-Probe) instead of Omron induction sensor 
  - [Purge bucket and brush](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/edwardyeeks/Decontaminator_Purge_Bucket_&_Nozzle_Scrubber) but also print the individual sheetstop and it is easy to get your magnetic print plate in the right place every time
  - MGN12H single X rail with reprinted parts to suit
  - Polycarbonate twinwall (8mm) side and top panels (much better insulation than 3mm acrylic) - details [here]( https://github.com/IconoclastXYZ/Voron/blob/main/articles/insulation.md)
  - [Quick removable side / top panel latches](https://github.com/richardjm/voron-parts/tree/main/voron-2.4/FilamentLatch)
  - [Removeable front hinges](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/ElPoPo/RemovableDoors) - but use the old engineering trick of a longer screw in the bottom hinge so that they are much easier to get back on
  - [Z chain guide mounted chamber thermistor](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/jeoje/Z_Chain_Guide_Thermistor_Mount)
  - [Deck support clips](https://github.com/VoronDesign/Voron-2/blob/Voron2.4/STLs/Panel_Mounting/deck_support_4mm_x8.stl)
  - [Rear chamber camera mount](https://www.thingiverse.com/thing:4756566) with [DFRobot USB 1080p camera](https://core-electronics.com.au/raspberry-pi-wide-angle-camera-module-seeed-studio.html)
  - [Sturdy handles](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/jeoje/Sturdy_Handles)
  - [Z axis tension mod from Edward Yeeks](https://github.com/edwardyeeks/VoronUsers/tree/master/printer_mods/edwardyeeks/V2.4_z_drive_motor_tensioner_mod)
  - [Matching skirts with power inlet and filter from Trident design](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/edwardyeeks/Tridentified_V2.4_Power_Inlet)
  - [Heating bed insulation](https://www.carbuilders.com.au/peel-stick-heat-shield)
  - [Raspberry Pi cooling fan](https://core-electronics.com.au/pimoroni-fan-shim-for-raspberry-pi.html)
  - LED strip lighting - [stuck to bars](https://www.thingiverse.com/thing:4933314/files)
  - With [cable cover for top end of Z belts](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/samwiseg0/corner_cable_hide) or [this better one](https://github.com/VoronDesign/VoronUsers/blob/ad3b6e1f34209fbf31f515cbb76d94880a948f3c/printer_mods/Dr-Info/corner_cable_cover_with_drop_down_holes/README.md)
  - [Cable cover for the bottom of the z belt](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Akio/cable_routing_z_belt_cover) or https://www.printables.com/model/84736-z-belt-cover-a-for-voron-24
  - [Better cooling head, ABBN 30](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Badnoob/AB-BN)
  - [Gantry backing bars](https://github.com/tanaes/whopping_Voron_mods/tree/main/extrusion_backers) to stop bimetallic strip effect and warping, purchased on [AliExpress](https://www.aliexpress.com/item/1005003779041015.html?spm=a2g0o.order_list.0.0.21ef180202r18o), also need new [XY chain riser](https://github.com/tanaes/whopping_Voron_mods/blob/main/extrusion_backers/STLs/XY_cable_chain_bridge-3hole-3mm_backer.stl) or some washers 
  - [Pin mod for gantry](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/hartk1213/Voron2.4_Trident_Pins_Mod) - but just did the xy for now
  - [Replace front z idlers with Rama design](https://github.com/Ramalama2/Voron-2-Mods/tree/main/Front_Idlers) but could have used the new design from [2.4r2](https://github.com/VoronDesign/Voron-2/tree/Voron2.4/STLs/Gantry/Front_Idlers)
  - Change Z mount to use [spherical bearings](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/hartk1213/Voron2.4_GE5C), tried IGUS, but too much stiction so using metal ones. Could have used nylock nuts (per Andrew Ellis) - now there is no friction on z-adjust. Checked the original parts and they had significant wear / catch marks!
  - ~~ADXL mounting for [klipper resonance compensation](https://www.klipper3d.org/Measuring_Resonances.html) - actually no problem. Just use a longer screw for any part of the print head and it works. No fancy mount required and it comes off afterwards anyway.~~ no need as it is built into the EBB36 CanBUS board
  - Wago clip mounts to improve wiring
  - [Improved Raspberry Pi mount](https://github.com/MotorDynamicsLab/LDOVoron2/blob/main/STLs/beefy_raspberry_bracket.stl), needs extra [DIN mount](https://github.com/VoronDesign/Voron-2/blob/Voron2.4/STLs/Electronics_Bay/pcb_din_clip_x3.stl)
  - CAN Bus board from [BigTreeTech](https://www.aliexpress.com/item/1005004243374113.html) with the [GitHub and manual](https://github.com/bigtreetech/EBB/)
  - [Raspberry Pi CAN Bus board to go with HUVUD](https://learn.sb-components.co.uk/RS485-CAN-HAT)
-- Add to /boot/config.txt (note the need for the \[all\] otherwise it can slip under Pi2, Pi3 or Pi4 and not work
```
[all]
dtparam=spi=on
dtoverlay=mcp2515-can0,oscillator=12000000,interrupt=25,spimaxfrequency=2000000
```
- With more info on how to setup CAN Bus [here](https://www.klipper3d.org/CANBUS.html)
- Frame thermistor (bare 3950) for doing thermal expansion compensation - mounted rear left, tucked inside the rail and held in with insulating foam so that it gives a good reading of the actual frame and not the (hotter) chamber
- [BTT Smart Filament Sensor](https://biqu.equipment/products/btt-sfs-v1-0-smart-filament-sensor-detection-stuck-blocking-filament-module) and [mount](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Empusas/BTT_Filament_Motion_Sensor_Mount) since the run-out sensor currently does not detect jams, which didn't work out well
- [Side entry for filament](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/120decibell/exhaust_housing_side_entry) which makes for a much better path paird with the BTT smart filament sensor, above
- Stealthburner and clockwork 2 - https://vorondesign.com/voron_stealthburner using and LDO motor
- Changing to an [umbilicus](https://github.com/IconoclastXYZ/Voron/blob/main/articles/Umbilical_conversion.md)
- Rear umbilical mount and Y endstop relocation from [Reprapster](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Minsekt/Rear_Umbilical)
- Stealthburner Umbilical cover from [majarspeed](https://github.com/majarspeed/Misc-Voron/tree/main/StealthBurner%20Umbilical%20cover)
- [Front top camera](https://core-electronics.com.au/lattepanda-5mp-uvc-camera.html) and [mount](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/chri.kai.in/Angry_CAM_USB)
- Rear under bed temperature sensor near the edge to better approximate when the bed had equilibrated (15C less at the edge underneath than from the sensor centrally under the heater pad)
- ~~[Bondtech LGX Lite extruder](https://www.bondtech.se/product/lgx-lite-large-gears-extruder/) with [this mount](https://github.com/Eytecz/LGX_Lite_Stealthburner_CW2_style_mount), which ends up weighing 183g with the mount and LDO motor vs 156g for the stock CW2~~ - does not grip PA6 CF at all well, extra slippage and poor surface finish, trying other options
- [Front top camera mount](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/chri.kai.in/Angry_CAM_USB) for a slimline [USB Camera](https://core-electronics.com.au/lattepanda-5mp-uvc-camera.html) because having to of the same cameras causes a conflict on the Raspberry Pi and only one is ever found
- [Voron Tap](https://github.com/VoronDesign/Voron-Tap) endstop and z-probe
- 3 wire hotend fan with RPM monitoring, with more info [here](https://forum.vorondesign.com/threads/ebb36-3-wire-fan-speed.83/)
- changed to Orbiter 2.0 extruder and used this [modified stealthburner cover](https://www.printables.com/model/345237-voron-stealthburner-orbiter-v20/files) and [mount](https://github.com/sneakytreesnake/StealthOrbiter) and [this](https://www.printables.com/model/316984-ebb36-mount-with-cable-strain-relief-for-the-orbit) or [this]() mount for the EBB36 board. Alternatively use [this](https://github.com/elcrni/Voron-Mods/tree/main/Orbiter_2.0_SB_CW2_Enclosed) enclosed cover

</details>
  
<details>
  <summary>Software - many from Andrew Ellis</summary>
  
  - lcd_tweaks.cfg
  - ~~z_calibration.cfg using [Klicky probe](https://github.com/protoloft/klipper_z_calibration#command-calibrate_z)~~ Now using Voron Tap
  - Github autocommit
  - Change color of Stealthburner and Main [leds](https://github.com/MapleLeafMakers/KlipperMacros) to show extruder and bed temperature
  - Mainsail [timelapse.cfg](https://github.com/mainsail-crew/moonraker-timelapse)
  - Fan control for Octopus - temperature controlled
  - Fan control for exhaust fan - keeps more stable chamber temp
  - Thermal expansion compensation from ~~[AlchemyEngine](https://github.com/alchemyEngine/klipper_frame_expansion_comp). Then to query the compensation `QUERY_FRAME_COMP`~~ - now built into Klipper
  - Simplying MCU klipper updates:
```
cd ~/klipper/
make clean KCONFIG_CONFIG=config.octopus
make menuconfig KCONFIG_CONFIG=config.octopus
make KCONFIG_CONFIG=config.octopus

sudo service klipper stop
make flash FLASH_DEVICE=/dev/serial/by-id/usb-Klipper_stm32f446xx_430011000650535556323420-if00
sudo service klipper start
```
  - Then for the BTT EBB CANBus Board (making sure you choose the right version as the CANBus pins have changed between [versions](https://github.com/bigtreetech/EBB))- after setting it up with [CANBoot](https://github.com/Arksine/CanBoot), explained [here](https://www.youtube.com/watch?v=_FELCN8CbWA):
```
cd ~/klipper/
make clean KCONFIG_CONFIG=config.ebb
make menuconfig KCONFIG_CONFIG=config.ebb
make KCONFIG_CONFIG=config.ebb
  
cd ~/klipper/lib/canboot
python3 flash_can.py -i can0 -f ~/klipper/out/klipper.bin -u d3e7f0c00d1a
```
- Just remember that sometimes the Pi will not find the MCU after a service stop and new make, requiring a power cycle of the whole system - much time wasted figuring this one out!
- [Moonraker Telegram integration](https://github.com/Raabi91/moonraker-telegram) to send message to and from the printer and getr status updates

</details>

## ToDo
- Fix the `controller_fan.py` script so that controller fans do not always come on with any stepper motor
  
## Under consideration
- [5.5 inch OLED display](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/sttts/Waveshare-5.5-inch-HDMI-AMOLED)
- Moonraker Telegram plugin to send updates on print status - https://github.com/Raabi91/moonraker-telegram
- [Plug panel](https://github.com/tanaes/whopping_Voron_mods/blob/main/side_skirts/STLs/side_skirt-plug_panel-350.stl) for external connections to the Pi, but need to find out what the holes are sized for?
- How to [automate Klipper updates](https://docs.vorondesign.com/community/howto/drachenkatze/automating_klipper_mcu_updates.html)
-- For this you will need to add an entry into the `~/klipper/scripts/spi_flash/board_defs.py` file for the BTT Octopus 1.1
```
'btt-oct-1.1': {
        'mcu': "stm32f446xx",
        'spi_bus': "spi2",
        "cs_pin": "PC12"
}
```
- Although this method won't work for me. I probably have the pin details wrong for the btt Octopus and anyway, if I edit the file Mainsail shows the klipper install as 'dirty' and if I update klipper it wipes these details.
- [Full coverage heater pad](https://uniqueprints.shop/shop/buildplate/voron-keenovo-bed-heater-fermio/)
- [Custom heater plate with slot for top of plate temperature sensor](https://preciseprinterparts.com/voron-cast-aluminum-printer-bed-350mm-vor-ver-24-and-18.html)
- [Kinematic bed mount](https://github.com/tanaes/whopping_Voron_mods/tree/main/kinematic_bed)
- [FYSETC ultralight X rail](https://www.aliexpress.us/item/3256804719096286.html) with the appropriate mounting blocks from [here](https://github.com/GiulianoM/Fystec-Voron-X-Block), [here](https://www.thingiverse.com/thing:5671339) or [here](https://www.teamfdm.com/files/file/641-light-x-beam-mounting-block/), with the [M5 heat inserts](https://www.amazon.com/M5x5-8mm-OD7-1mm-Threaded-Plastic-Staking/dp/B08T9W17CR)
- [Twin fan filter / chamber fan](https://github.com/nateb16/VoronUsers/tree/master/printer_mods/nateb16/THE_FILTER/THE_FILTER_STANDARD_BED_SPACING) possibly better than nevermore, which does not fit my setup
  
## Utility and Test prints
- Voron test cube
- Andrew Ellis print tining guide and parts
- Filament swatches - https://www.printables.com/model/27814
- [Bridging tests](https://www.thingiverse.com/thing:476845/files)
- [Temperature tower models](https://www.thingiverse.com/thing:2729076)
- [Hot end flow test generator](https://hotend-flow-tester.netlify.app/)
- [Pressure advance calibration pattern generator](https://realdeuce.github.io/Voron/PA/pressure_advance.html)
- [Variety of Wago mounts](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/LoganFraser/WagoMounts)

## [Filament settings for the Voron](/filaments/Polymaker-filament-settings.md)
- Polymaker Polylite PA6-CF
- Polymaker Polylite ASA
- Polymaker Polylite PLA
- Polymaker Polylite PC

## Other resources
- [BTT Octopus pinout](https://github.com/VoronDesign/VoronUsers/tree/master/firmware_configurations/klipper/revnull/btt_octopus_pins)
- [Great article on the Octopus with lots of pinouts, etc.](https://3dwork.io/en/btt-octopus/)
- [BTT Schematic from Thomas White](/images/Octopus34-2048x1124.png)
- [Klipper config reference](https://www.klipper3d.org/Overview.html)
- [G-code Wiki](https://reprap.org/wiki/G-code)
- [Nero 3DP Tutorial video on deracking](https://www.youtube.com/watch?v=cOn6u9kXvy0)
- [Plating tool for optimising printing plates](https://github.com/Rhoban/Plater), but the Windows version needs to come from [here](https://drive.google.com/drive/folders/1USaJTZzJk_7KIQr8ctoPnoI9gQ6FYcY9) which was listed on the Issues page
- CloudCompare tool - finding differences in models / meshes (and lots more!) - https://www.cloudcompare.org/
- Voron mechanical construction manuals - [current and prior versions](https://docs.vorondesign.com/build/mechanical/#v2)
- [Great list of Voron Mods](https://github.com/Amarpal89/VoronUsers/tree/master/printer_mods)
- JINJA [Template Reference](https://jinja.palletsprojects.com/en/3.0.x/templates/) - used in klipper macros for additional control / automation

## Slicer information
- After trying them all (IdeaMaker, PrusaSlicer, Cura (various versions), others I can't remember) settled on SuperSlicer
- Using base profile from Andrew Ellis (pif profile) but customising for my printer and filaments

### Slicer tweaking
- Start slower than you would like, but Andrew's velocities are not bad at all
- Changed settings for overhangs to slow down much more and for PLA to cool agressively - much better overhangs
- Supports - automatic puts them *everywhere* which is a pain, paint them on only as required. Slower overhang head speeds are much better than removing lots more supports
- Suggested support settings from https://forum.prusa3d.com/forum/prusaslicer/prusaslicer-hard-to-remove-supports/
-- 0.25mm z distance.
-- 75% xy distance.
-- 3mm support spacing.
-- 4 interface layers.
-- 0.2mm interface layer spacing.
-- I think those are the key settings. Exposed support pulls off easily. Any entangled with the part (e.g. between legs) requires cutting to separate before pulling apart. 

These settings are working well for me with PLA and both 0.25 and 0.40mm nozzles. Haven't tried much else.

### Filament based settings
- Adjust the Z-offset based on the filament
- SET_GCODE_OFFSET Z_ADJUST=0.05 MOVE=1 - moves it up 0.05mmm, used for ASA on a hot bed in the Filament Custom G-code settings
