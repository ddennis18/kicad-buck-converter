# DC-DC Buck Converter

KiCad design for an adjustable, non-isolated step-down DC-DC converter based on the TI LM2596S-ADJ switching regulator.

## Design Overview

- Adjustable output voltage set with RV1 (10 kOhm potentiometer).
- LM2596S-ADJ regulator with an SS34 Schottky catch diode and 47 uH inductor.
- Single-pin 2.54 mm through-hole terminals for input and output.
- Design credit in the schematic: Osemwegie Osemwonken Darius Dennis (D18S).

The LM2596 family is a 3 A regulator, but that is not a guarantee of 3 A continuous output from this board. Usable input/output voltage and current depend on the regulator datasheet limits, component ratings, PCB thermal performance, and cooling. Confirm these limits before use.

## Connections

| Reference | Connection |
| --- | --- |
| J1 | VIN, positive input |
| J2 | GND, input return |
| J3 | VOUT, positive regulated output |
| J4 | GND, output return |

The converter is non-isolated; input and output grounds are common. Check polarity before applying power and verify the output voltage with a meter before connecting a load.

## Project Files

| File | Description |
| --- | --- |
| `buck-converter.kicad_pro` | KiCad project settings |
| `buck-converter.kicad_sch` | Circuit schematic |
| `buck-converter.kicad_pcb` | PCB layout |
| `buck-converter.csv` | Schematic-generated bill of materials |
| `Datasheets/lm2596.pdf` | LM2596 datasheet |

Open `buck-converter.kicad_pro` in KiCad to view or edit the design. The CSV BOM contains the component values, footprints, and an SS34 datasheet link.

## Bring-Up Notes

1. Review the schematic and board layout, and run KiCad electrical-rule and design-rule checks before fabrication or assembly.
2. Confirm component polarity and orientation, especially C2/C3, D1/D2, and U1.
3. Start with a current-limited input supply. Measure VOUT and adjust RV1 before connecting a load.
4. Check regulator, diode, and inductor temperatures under load; reduce load or improve cooling if they become excessive.