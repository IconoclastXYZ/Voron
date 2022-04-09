# FORMBOT 3D Suggestions and Learning Points

## A few things I noticed during the build
- M3 x 12mm SHCS - short 4 - current spec and even 2.4r1 requires more than supplied
- M5 x 40mm SHCS - couple with unfinished heads, but enough spares
- Z axis Gates belts - spec says they should be longer than you supplied, and they are too short to easily tie up at their ends. Only needs another 5cm each
- 3M UHB tape is not in fact high bond
- Chamber base plate (black plastic) is ~2mm oversized to the supplied frame and to the spec
- SSR connector wires were terminated incorrectly for the Octopus board
- Hotend E motor wire was short - only just made it
- Combined 240v socket and switch is pressfit, but does not fit the printed parts, which were to spec
 
## A few improvements that could be made to the kit
### Tell people EXACTLY what is supplied
- Hall effect sensor board and wiring are supplied for the X & Y stops - this changes the printed parts required
- Z endstop board and wiring is supplied - this changes the printed parts required
- Hotend thermistor - specify the type / model, needed when setting up Klipper
- Heater bed thermistor - specify the type  model, needed when setting up klipper
- Inductive probe - specify modela and whether NO or NC is supplied, needed when setting up Klipper
- What type of 240v socket/switch is supplied
 
### Some inclusion that would be great, or things to do yourself
- Blue Locktite or equivalent
- GND bridging wire to get common ground for the 24v and 5v PSUs
- Separate 240v socket and switch, as now recommended
- Z end stop pin WITH the flat ground in it so it can be retained with a grub screw
