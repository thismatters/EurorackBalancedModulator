# Balanced Modulator

The Balanced Modulator combines to audio signals to create interesting overtones, not unlike a ring modulator but lacking many sidebands.

The circuit here is based on the [Yusynth Double Balanced Modulator](https://yusynth.net/Modular/EN/RINGMOD/index.html) with minor tweaks to make it more Eurorack friendly. The changes I've made are thus:
* Selected resistors appropriate for +/-12V rails,
* Added polarity protection so that a backward power header doesn't fry anything (twin series schotty diodes: BAT54SL),
* Full surface mount design,
* Reduced module to a single balanced modulator.

The Yusynth page is a treasure trove of information about this circuit that I am too amateur to claim as my own; please read that outstanding page before using this circuit. The page provides many details and other implementations of this circuit that you may find suitable.

The KiCAD project here uses the library/footprints [found in my companion repo](https://github.com/thismatters/EurorackKiCAD).

## Width

12hp on an Intellijel 1U rack.

## Inputs

Jacks:
- Carrier Signal: `A sin(f_1 t)`
- Modulating Signal: `B sin(f_2 t)`

## Outputs

Output jack for modulated signal: `A sin((f_1 + f_2) t) + A sin((f_1 - f_2) t)`

## Adjustment

* Set up the module to be in "AC" mode (see below).
* Set a VCO to output 1000Hz sine wave and connect it to the "carrier" input.
* Connect an oscilloscope to the output of the module.
* Adjust RV2 until the module output is flat.
* Move the VCO output to the "modulating" input.
* Adjust RV1 until the module output is flat.

### Choose Operating Mode

There are three sets of jumpers for setting whether the inputs and outputs will be AC or DC coupled.
Use three jumpers to choose how the signals will be coupled.

## Vendors

There are part numbers in the [BOM](balanced-modulator.csv) for many of the parts (not for basic passives though) at the following vendors:

* [Mouser](https://www.mouser.com): Needs no introduction. Get your ICs from here (or [digikey](https://www.digikey.com)).
* [Tayda Electronics](https://www.taydaelectronics.com/): Good supplier for passive components; audio jacks, and potentiometers. Their audio jacks are slightly smaller than the thonkiconn from thonk.
* [Love My Switches](https://lovemyswitches.com/): Has [really good knobs](https://lovemyswitches.com/anodized-aluminum-knob-the-lo-fi-1-4-smooth-shaft-12-5mm-od/) to go on those potentiometers!
* [OSHPark](https://oshpark.com/): Fast and (relatively) cheap PCB manufacturer. [V0 PCB works great!](https://oshpark.com/shared_projects/MmM817Fr)
