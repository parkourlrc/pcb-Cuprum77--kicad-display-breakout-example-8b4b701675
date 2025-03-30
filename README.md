# kicad-display Breakout example

This repository contains a simple breakout board for a 1.69" IPS LCD with capacitive touch, and serves as an example of the KiCad project structure.

It was intended to be used with the following display from [AliExpress](https://aliexpress.com/item/1005005238299349.html), however this flat-flex cable is not solderable, and requires a FPC connector to be soldered onto the PCB.
This was originally an oversight on my part, and the PCB that was produced did not feature this footprint, which required manual rework of soldering individual wires directly to the FPC. This version should be fixed, although it has never been produced.

## Requirements

- [KiCad Version 9 or later](https://www.kicad.org/)


## Pulling the repository

Remember to pull recursive submodules to include the display library if you are using git to clone the repository!

```bash
git submodule update --init --recursive
```


## Bill of Materials (BOM)

| Reference | Value | Quantity | Source |
|---|---|---|---|
| DS1 | 1.69" IPS LCD with capacitive touch, FPC connector with 0.5mm pitch | 1 | [Digikey](https://www.digikey.no/en/products/detail/amphenol-cs-fci/SFV18R-4STBE1HLF/4270611) |
| C1, C2, C3 | 100 nF 0603 | 3 | Digikey |
| R1 | 1k 0603 | 1 | Digikey |
| R2 | 10k 0603 | 1 | Digikey |
| R3 | 0R 0603[^1] | 1 | Digikey |
| J1 | 1x12 2.54mm Header | 1 | Digikey |

[^1]: Note that R3 can be shorted by a solder bridge if you don't have a 0R resistor. This is an optional resistor to limit the current to the LCD backlight. The backlight consists of 3 LEDs in parallel and can pull up to 60 mA. 
With a 3V3 supply and a BJT as a switch, the voltage over the LED will be slightly below the nominal forward voltage of 3 V.

## Affiliation

I am in no way affiliated with any of the companies mentioned in this document. The links to the products are provided for convenience and are not endorsements of any kind. The products may be available from other sources, and I encourage you to shop around for the best price and availability.

The PCB however were paid for by Aisler as a part of a single-time sponsorship through a store-credit. I am under no contract or obligation to promote their services, and I have no financial interest in their success.

## License

This project is licensed under CERN Open Hardware License Version 2 - Strong Reciprocity (CERN-OHL-S-2.0). See [LICENSE](LICENSE) for more details.