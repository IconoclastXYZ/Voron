# Voron
Build details, tips, tricks and traps for the 2.4 r1 - r2

# Base build
## Formbot 3D kit - supplied to 2.4r1 specs but with
- hall effect XY endstops
- z endstop circuit board
- Phaetus Dragon HF hotend
- Octopus 1.1
- Raspberry Pi 3B+ (1GB RAM)

There were a few traps for young players in the Formbot 3D build, outlined [here](https://github.com/IconoclastXYZ/Voron/blob/main/articles/formbot_build.md)

## What to print?
Third party (Etsy) printed parts in ASA to 2.4r1 with a few extra needed for the MGN12H rail

Turns out that they sponaneously printed the new (r2) dine rail mounts for components, which is great

Quite a few other parts from r2 can be printed for r1 kits and only improve them, eg. z-axis and ab-axis idlers, all the skirts, all electronics mounts

## Things I wish I had known BEFORE starting to assemble the Voron
Lots of others build lists and hints exist, with my particular blind spots / learning points listed [here](https://github.com/IconoclastXYZ/Voron/blob/main/articles/build_lessons.md)
  
## Physical mods
- Klicky mod instead of Omron induction sensor - https://github.com/jlas1/Klicky-Probe
- Purge bucket and brush
- MGN12H single X rail with reprinted parts to suit
- Polycarbonate twinwall (8mm) side and top panels (much better insulation than 3mm acrylic) - details [here]( https://github.com/IconoclastXYZ/Voron/blob/main/articles/insulation.md)
- Quick removable side / top panel latches - https://github.com/richardjm/voron-parts/tree/main/voron-2.4/FilamentLatch
- Removeable front hinges - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/ElPoPo/RemovableDoors
- Z chain guide mounted chamber thermistor - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/jeoje/Z_Chain_Guide_Thermistor_Mount
- Deck support clips - https://github.com/VoronDesign/Voron-2/blob/Voron2.4/STLs/Panel_Mounting/deck_support_4mm_x8.stl
- Rear chamber camera mount with DFRobot USB 1080p camera - https://3dmixers.com/m/181820-voron-24-camera-mount and https://core-electronics.com.au/raspberry-pi-wide-angle-camera-module-seeed-studio.html
- Sturdy handles - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/jeoje/Sturdy_Handles
- Z axis tension mod from Edward Yeeks
- Matching skirts with power inlet and filter from Trident design - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/edwardyeeks/Tridentified_V2.4_Power_Inlet
- Heating bed insulation
- Raspberry Pi cooling fan - https://core-electronics.com.au/pimoroni-fan-shim-for-raspberry-pi.html
- LED strip lighting - held by these - https://www.thingiverse.com/thing:4933314/files
- With cable cover for top end of Z belts - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/samwiseg0/corner_cable_hide
- And able cover for the bottom of the z belt - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Akio/cable_routing_z_belt_cover or https://www.printables.com/model/84736-z-belt-cover-a-for-voron-24
- Better cooling head, ABBN 30 - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Badnoob/AB-BN 
  
## Software mods - many from Andrew Ellis
- lcd_tweaks.cfg
- z_calibration.cfg using Klicky probe - https://github.com/protoloft/klipper_z_calibration#command-calibrate_z
- Github autocommit
- Mainsail timelapse.cfg
- Fan control for Octopus - temperature controlled
- Fan control for exhaust fan - keeps more stable chamber temp

## ToDo
- Change Z mount - either stubby mount with nylock nuts (Andrew Ellis) or using spherical bearings - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/hartk1213/Voron2.4_GE5C
- Replace front z idlers - either with new 2.4r2 design (https://github.com/VoronDesign/Voron-2/tree/Voron2.4/STLs/Gantry/Front_Idlers) or the Rama design (https://github.com/Ramalama2/Voron-2-Mods/tree/main/Front_Idlers)
  
## Under consideration
- Frame expansion compensation - https://github.com/alchemyEngine/klipper_frame_expansion_comp
- 5.5 inch OLED display - https://voronregistry.com/mods/sttts-waveshare55inchhdmiamoledmount
- Chamber heater - https://www.teamfdm.com/files/file/455-chamber-heater/
- Wago clip mounts to improve wiring
- Improved Raspberry Pi mount - https://github.com/MotorDynamicsLab/LDOVoron2/blob/main/STLs/beefy_raspberry_bracket.stl (needs extra DIN mount - https://github.com/VoronDesign/Voron-2/blob/Voron2.4/STLs/Electronics_Bay/pcb_din_clip_x3.stl)
- Stealthburner and clockwork 2 - https://vorondesign.com/voron_stealthburner when it is out of beta
  
## Test prints
- Voron test cube
- Andrew Ellis print tining guide and parts
- Filament swatches - https://www.printables.com/model/27814

## Other resources
- BTT Octopus pinout - https://github.com/VoronDesign/VoronUsers/tree/master/firmware_configurations/klipper/revnull/btt_octopus_pins


  
  
  
  
  
