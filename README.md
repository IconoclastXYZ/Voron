# Voron
Build details, tips, tricks and traps for the 2.4 r1 - r2

# Base build
## Formbot 3D kit - supplied to 2.4r1 specs but with
- hall effect XY endstops
- z endstop circuit board
- Phaetus Dragon HF hotend
  
Third party (Etsy) printed parts in ASA to 2.4r1
  
## Physical mods
- Klicky mod instead of Omron induction sensor - https://github.com/jlas1/Klicky-Probe
- Purge bucket and brush
- MGN12H single X rail with reprinted parts to suit
- Polycarbonate twinwall (8mm) side and top panels (much better insulation than 3mm acrylic) - see below
- Quick removable side / top panel latches - https://github.com/richardjm/voron-parts/tree/main/voron-2.4/FilamentLatch
- Removeable front hinges - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/ElPoPo/RemovableDoors
- Z chain guide mounted chamber thermistor - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/jeoje/Z_Chain_Guide_Thermistor_Mount
- Deck support clips - https://github.com/VoronDesign/Voron-2/blob/Voron2.4/STLs/Panel_Mounting/deck_support_4mm_x8.stl
- Rear chamber camera mount with DFRobot USB 1080p camera
- Sturdy handles - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/jeoje/Sturdy_Handles
- Z axis tension mod from Edward Yeeks
- Matching skirts with power inlet and filter from Trident design - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/edwardyeeks/Tridentified_V2.4_Power_Inlet
- Heating bed insulation
  
## Software mods - many from Andrew Ellis
- lcd_tweaks.cfg
- z_calibration.cfg using Klicky probe - https://github.com/protoloft/klipper_z_calibration#command-calibrate_z
- Github autocommit
- Mainsail timelapse.cfg

## ToDo
- Change Z mount - either stubby mount with nylock nuts (Andrew Ellis) or using spherical bearings - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/hartk1213/Voron2.4_GE5C
- Replace front z idlers - either with new 2.4r2 design (https://github.com/VoronDesign/Voron-2/tree/Voron2.4/STLs/Gantry/Front_Idlers) or the Rama design (https://github.com/Ramalama2/Voron-2-Mods/tree/main/Front_Idlers)
  
## Under consideration
- Frame expansion compensation - https://github.com/alchemyEngine/klipper_frame_expansion_comp
- LED strip lighting - held by these - https://www.thingiverse.com/thing:4933314/files
- With cable cover for top end of Z belts - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/samwiseg0/corner_cable_hide
- And able cover for the bottom of the z belt - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Akio/cable_routing_z_belt_cover or https://www.printables.com/model/84736-z-belt-cover-a-for-voron-24
- 5.5 inch OLED display - https://voronregistry.com/mods/sttts-waveshare55inchhdmiamoledmount
- Chamber heater - https://www.teamfdm.com/files/file/455-chamber-heater/
- Wago clip mounts to improve wiring
- Improved Raspberry Pi mount - https://github.com/MotorDynamicsLab/LDOVoron2/blob/main/STLs/beefy_raspberry_bracket.stl (needs extra DIN mount - https://github.com/VoronDesign/Voron-2/blob/Voron2.4/STLs/Electronics_Bay/pcb_din_clip_x3.stl)
- Better cooling head, either ABBN 30 - https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Badnoob/AB-BN or Stealthburner - https://vorondesign.com/voron_stealthburner when it is out of beta
  
## Test prints
- Voron test cube
- Andrew Ellis print tining guide and parts
- Filament swatches - https://www.printables.com/model/27814

## Stats on insulation acrylic vs polycarbonate twinwall
For U-values, lower is better

### Twinwall polycarbonate sheet
- 8mm - U-value 3.3
- 10mm - U-value 2.9
- Ref: https://vicwest.com/wp-content/uploads/2019/07/SUNLITE_En_Technical_Guide_61353_Web_1.pdf

### Perspex / acrylic
- 3mm - U-value 5.2
- 5mm - U-value 4.9
- Ref: https://www.allplastics.com.au/component/docman/doc_download/93-allplastics-perspex-datasheet-for-glazing-pdf?Itemid=

  
  
  
  
  
