# My Setup
## Base build - Voron V2.4 350mm (with mostly r2 parts)
### Formbot 3D kit - supplied to 2.4r1 specs but with
- hall effect XY endstops - changed to microswitches for reliability
- z endstop circuit board - gone with the Voron Tap
- Phaetus Dragon HF hotend - changed to Phaetus Rapido
- [BigTreeTech Octopus 1.1](https://www.biqu.equipment/products/bigtreetech-octopus-v1-1)
- Raspberry Pi 3B+ (1GB RAM) - changed to RPi 4 4GB

### Printed parts
- Third party (Etsy) printed parts in ASA to 2.4r1 with a few extra needed for the MGN12H rail
- Turns out that they spontaneously printed the new (r2) din rail mounts for components, which is great
- Quite a few other parts from r2 can be printed for r1 kits and only improve them, eg. z-axis and ab-axis idlers, all the skirts, all electronics mounts

## Toolhead
- Stealthburner and clockwork 2 - https://vorondesign.com/voron_stealthburner using and LDO motor
- Phaetus Rapido Plus hotend - with integrated 115W heater and P1000 thermistor
- [Voron Tap](https://github.com/VoronDesign/Voron-Tap) endstop and z-probe
- Changing to an [umbilicus](https://github.com/IconoclastXYZ/Voron/blob/main/articles/Umbilical_conversion.md)
- changed to Orbiter 2.0 extruder and used this [modified stealthburner cover](https://www.printables.com/model/345237-voron-stealthburner-orbiter-v20/files) and [mount](https://github.com/sneakytreesnake/StealthOrbiter) and [this](https://www.printables.com/model/316984-ebb36-mount-with-cable-strain-relief-for-the-orbit) or [this]() mount for the EBB36 board. Alternatively use [this](https://github.com/elcrni/Voron-Mods/tree/main/Orbiter_2.0_SB_CW2_Enclosed) enclosed cover
- 3 wire hotend fan with [RPM monitoring](https://www.klipper3d.org/Config_Reference.html#heater_fan) and using the guide from Andrew Ellis and the linked [macro](https://ellis3dp.com/Print-Tuning-Guide/articles/useful_macros/hotend_fan_monitoring.html), with more info [here](https://forum.vorondesign.com/threads/ebb36-3-wire-fan-speed.83/), which explained why the first time I did it it blew the BTT EBB36 board. Now it has a signal diode inline with the endstop pin. Otherwise, the endstop supplies 7.8mA constantly, which is enough to drive the fan. A 5K resister drops this to 1.8mA but it then does not sense rotation.

## Print axes
- MGN12H single X rail with reprinted parts to suit
- [Z axis tension mod from Edward Yeeks](https://github.com/edwardyeeks/VoronUsers/tree/master/printer_mods/edwardyeeks/V2.4_z_drive_motor_tensioner_mod)
- [Pin mod for gantry](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/hartk1213/Voron2.4_Trident_Pins_Mod) - but just did the xy for now
- [Replace front z idlers with Rama design](https://github.com/Ramalama2/Voron-2-Mods/tree/main/Front_Idlers) but could have used the new design from [2.4r2](https://github.com/VoronDesign/Voron-2/tree/Voron2.4/STLs/Gantry/Front_Idlers)
- Change Z mount to use [spherical bearings](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/hartk1213/Voron2.4_GE5C), tried IGUS, but too much stiction so using metal ones. Could have used nylock nuts (per Andrew Ellis) - now there is no friction on z-adjust. Checked the original parts and they had significant wear / catch marks!
- [Gantry backing bars](https://github.com/tanaes/whopping_Voron_mods/tree/main/extrusion_backers) to stop bimetallic strip effect and warping, purchased on [AliExpress](https://www.aliexpress.com/item/1005003779041015.html?spm=a2g0o.order_list.0.0.21ef180202r18o), also need new [XY chain riser](https://github.com/tanaes/whopping_Voron_mods/blob/main/extrusion_backers/STLs/XY_cable_chain_bridge-3hole-3mm_backer.stl) or some washers 

## Chamber
- Polycarbonate twinwall (8mm) side and top panels ([much better insulation than 3mm acrylic]( https://github.com/IconoclastXYZ/Voron/blob/main/articles/insulation.md))
- Active heating using a [DBK FGC1515.2R CIRRUS 230W Rail 115/230V Heater](https://dbkusa.com/collections/ptc-enclosure-fan-heaters/products/cirrus40?variant=39257500516410), controlled using a second solid state relay
- [Quick removable side / top panel clips](https://github.com/Annex-Engineering/Annex-Engineering_User_Mods/tree/main/Printers/All_Printers/annex_dev-Panel_2020_Clips_and_Hinges)
- [Removeable front hinges](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/ElPoPo/RemovableDoors) - but use the old engineering trick of a longer screw in the bottom hinge so that they are much easier to get back on
- [Sturdy handles](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/jeoje/Sturdy_Handles)
- LED strip lighting - [stuck to bars](https://www.thingiverse.com/thing:4933314/files)
- With [cable cover for top end of Z belts](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/samwiseg0/corner_cable_hide) or [this better one](https://github.com/VoronDesign/VoronUsers/blob/ad3b6e1f34209fbf31f515cbb76d94880a948f3c/printer_mods/Dr-Info/corner_cable_cover_with_drop_down_holes/README.md)
- [Cable cover for the bottom of the z belt](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Akio/cable_routing_z_belt_cover) or https://www.printables.com/model/84736-z-belt-cover-a-for-voron-24
- [Deck support clips](https://github.com/VoronDesign/Voron-2/blob/Voron2.4/STLs/Panel_Mounting/deck_support_4mm_x8.stl)
- [Rear chamber camera mount](https://www.thingiverse.com/thing:4756566) with [DFRobot USB 1080p camera](https://core-electronics.com.au/raspberry-pi-wide-angle-camera-module-seeed-studio.html)
- [Front top camera](https://core-electronics.com.au/lattepanda-5mp-uvc-camera.html) and [mount](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/chri.kai.in/Angry_CAM_USB)
- [Front top camera mount](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/chri.kai.in/Angry_CAM_USB) for a slimline [USB Camera](https://core-electronics.com.au/lattepanda-5mp-uvc-camera.html) because having to of the same cameras causes a conflict on the Raspberry Pi and only one is ever found
- Frame thermistor (bare 3950) for doing thermal expansion compensation - mounted rear left, tucked inside the rail and held in with insulating foam so that it gives a good reading of the actual frame and not the (hotter) chamber
- [BTT Smart Filament Sensor](https://biqu.equipment/products/btt-sfs-v1-0-smart-filament-sensor-detection-stuck-blocking-filament-module) and [mount](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Empusas/BTT_Filament_Motion_Sensor_Mount) since the run-out sensor currently does not detect jams, which didn't work out well
- [Side entry for filament](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/120decibell/exhaust_housing_side_entry) which makes for a much better path paird with the BTT smart filament sensor, above
- Then some nice clips to hold down the cables [here](https://www.printables.com/model/118550-cable-clip-for-2020-extrusion/files), [here](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/evandepol/Voron2.4-Cable-clamps) and [here](https://www.printables.com/en/model/203062-ender-3-2020-extrusion-zip-tie-clips-imported-from/files)
  
## Print bed
- [Purge bucket and brush](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/edwardyeeks/Decontaminator_Purge_Bucket_&_Nozzle_Scrubber) but also print the individual sheetstop and it is easy to get your magnetic print plate in the right place every time
- [Heating bed insulation](https://www.carbuilders.com.au/peel-stick-heat-shield)
- Rear under bed temperature sensor near the edge to better approximate when the bed had equilibrated (15C less at the edge underneath than from the sensor centrally under the heater pad)

## Undercarriage
- [Matching skirts with power inlet and filter from Trident design](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/edwardyeeks/Tridentified_V2.4_Power_Inlet)
- [Raspberry Pi cooling fan](https://core-electronics.com.au/pimoroni-fan-shim-for-raspberry-pi.html)
- [Improved Raspberry Pi mount](https://github.com/MotorDynamicsLab/LDOVoron2/blob/main/STLs/beefy_raspberry_bracket.stl), needs extra [DIN mount](https://github.com/VoronDesign/Voron-2/blob/Voron2.4/STLs/Electronics_Bay/pcb_din_clip_x3.stl)
- CanBUS adaptor on the Raspberry Pi as described in the section on the [Umbilical Conversion](/articles/Umbilical_conversion.md)

## Software
- Start with [MainSail OS](https://docs-os.mainsail.xyz/), which includes all the main software components like Mainsail, Klipper, Moonraker, Crowsnest, Sonar, [Timelapse](https://github.com/mainsail-crew/moonraker-timelapse) and preinstalls [CanBoot](https://github.com/Arksine/CanBoot)
- [Github autocommit](https://docs.vorondesign.com/community/howto/EricZimmerman/BackupConfigToGithub.html) to backup the config to GitHub from MainSail
- [Moonraker Telegram integration](https://github.com/Raabi91/moonraker-telegram) to send message to and from the printer and get status updates
- 
- lcd_tweaks.cfg
- Change color of Stealthburner and Main [leds](https://github.com/MapleLeafMakers/KlipperMacros) to show extruder and bed temperature
- Fan control for Octopus - temperature controlled
- Fan control for exhaust fan - keeps more stable chamber temp
- Z-axis frame thermal expansion compensation - now built into Klipper

- [Klipper adaptive meshing and purging](https://github.com/kyleisah/Klipper-Adaptive-Meshing-Purging) which improved single part printing and also replaced my home grown fuzzy purge line and purge bucket macros

## [Klipper updating on the MCUs](https://github.com/IconoclastXYZ/Voron/blob/main/articles/klipper_updates.md)

