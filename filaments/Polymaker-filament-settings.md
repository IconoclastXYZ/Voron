# Polymaker Filament settings for the Voron 2.4r2

| Setting                       | PA6-CF | ASA   | PLA   | PC-Clear  | PolyWood   |
|-------------------------------|--------|-------|-------|-----------|------------|
| Filament                      |        |       |       |           |            |
| Extruder (first)              | 280    | 240   | 200   | 260       | 185        |
| Extruder (other)              | 275    | 240   | 195   | 260       | 185        |
| Bed (first)                   | 35     | 95    | 65    | 105       | 45         |
| Bed (other)                   | 35     | 95    | 60    | 105       | 45         |
| Chamber (C)                   | 25     | 40    | 0     | 40        | 0          |
| Extrusion X                   | 0.924  | 0.924 | 0.924 | 0.924     | 1.1        |
| Density                       | 1.17   | 1.03  | 1.03? | 1.03?     | 0.8        |
| Cooling                       |        |       |       |           |            |
| Default fan                   | 0%     | 0     | 80    | 0         | 100        |
| Bridge fan                    | 50%    | -1    | 100   | 20        | 100        |
| Short layer fan if time under | 20s    | 20    | 60    | 0         | 100        |
| Max fan                       | 0%     | 0     | 100   | 100       | 100        |
| V short layer time goal       | 15s    | 15    | 15    | 15        | 15         |
| Max speed reduction           | 90%    | 90    | 90    | 90        | 90         |
| Min print speed               | 10mm/s | 10    | 10    | 10        | 10         |
| Filament overrides            |        |       |       |           |            |
| Retraction length             | 2.6mm  | -     | -     | -         | 4mm        |
| Wiping                        |        |       |       |           | Retracting |
| Z_offset                      | 0.025mm|       |       |           |            |
| Bridge flow                   | 40%    |       |       |           |            |

## Other settings for all filaments

- All as per Andrew Ellis profile except
-- Bridge speed - 60mm/s
-- Flow ratio - bridge - 70%

## Learning curve notes
- PA6 CF likes less squish - 0.025mm less is not a bad start, and it really likes lower flow for bridges and slower speeds for printing, otherwise the surface finish gets really awful
- Most of the other filaments can cope with quite fast printing, especially for fill
