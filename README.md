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

## Things I wish I had known BEFORE starting to assemble the Voron
Lots of others build lists and hints exist, with my particular blind spots / learning points listed [here](https://github.com/IconoclastXYZ/Voron/blob/main/articles/build_lessons.md)
  
## [My current setup](https://github.com/IconoclastXYZ/Voron/blob/main/articles/my_setup.md)  
  
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
