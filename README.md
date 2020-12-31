# Ender i3 Pro

This reposity contains all of the modifications I have made to my Ender 3 Pro, which I now call the
Ender i3 Pro due to the heavy design inspiration of the Prusa i3 series on my [completely redesigned x-axis carraige](#x-carriage). 
This was forked from the official Creality Ender-3 repository, which does not include files for the 
Ender 3 Pro. However, the only files that are officially open sourced are for the Ender 3. The 
differences between the Ender 3 and Ender 3 Pro aren't that great, and so most of the mechanical 
upgrades that I have made are compatible with both the Ender 3 and the Ender 3 Pro, with few exceptions.

## Mechanical upgrades

The mechanical upgrades are in the [Ender-3 Mechanical/Ender-3 Upgrades/](Ender-3%20Mechanical/Ender-3%20Upgrades)
folder. Inside that folder are a series of other folders, each containing a different upgrade. I 
designed each of these upgrades using Solidworks 2019-2020.

Here is a description of each of the folders:

### [ABL](Ender-3%20Mechanical/Ender-3%20Upgrades/ABL)

This was an experimental upgrade that tried to add auto bed leveling using the z-axis microswitch
and an allen key that was attached to the x-axis carriage. In my testing, this did not work that 
well and was not accurate enough to produce usable measurements. 

### [Direct Drive](Ender-3%20Mechanical/Ender-3%20Upgrades/Direct%20Drive)

This simply repositioned the stock extruder system to be attached to the x-axis carriage. This was a
modification of (this adapter on thingiverse)[https://www.thingiverse.com/thing:3386628] that
was modified to fit the Hero Me cooling system. 

**DO NOT USE THIS OR THE HERO ME COOLING SYSTEM, ESPECIALLY IF YOU HAVE A V6 STYLE HOTEND**. 
If you look at the model, the heatsink fan duct does not direct air to the lowest fins on the hotend
heatsink, which is where cooling is needed **the most**. In my testing, I ran into tons of heat creep
issues when I used filament seceptible to heat creep such as Prusament PLA (Prusament PLA has been
extensively documented as seceptible to heat creep).

### [E3D V6](Ender-3%20Mechanical/Ender-3%20Upgrades/E3D%20V6)

This is simply a model of the E3D V6 hotend pulled from GrabCAD [here](https://grabcad.com/library/e3d-v6-hotend-3).
When you download it from GrabCAD, the mate (in Solidworks) between the heat break and the nozzle is incorrect, so 
the length of the entire hotend from the top of the heatsink to the tip of the nozzle is shorter than
it should be. After fixing that mate, the length of the entire hotend is correct. 

### [Radial Cooling Fan 50mm DC12V](Ender-3%20Mechanical/Ender-3%20Upgrades/Radial%20Cooling%20Fan%2050mm%20DC12V)

This is just a model of a generic 5015 blower fan.

### [Rear Electronics Case](Ender-3%20Mechanical/Ender-3%20Upgrades/Rear%20Electronics%20Case)

This is a rear electronics case meant to replace the sheet metal electronics enclosure of the stock
Ender 3 and Ender 3 Pro. On the Ender 3 Pro, the electronics enclosure is opened from the bottom, 
making it absurdly annoying to change any of the wiring (for example, replacing the mainboard). 
This rear electronics case was heavily inspired by 
[Teaching Tech's rear electronics case](https://www.thingiverse.com/thing:3688967) as well, but
I designed one myself just for design practice and because I wanted to make a few modifications, 
including:

* Cable chain clips that work with [this](https://www.thingiverse.com/thing:2920060) popular printable
cable chain for the Ender 3
* Fan that points directly at the mainboard
* Cable tie mounting points
* Buck converter mounting points, which enables the Ender 3 power supply to power a Raspberry Pi.

One known issue is that the tolerances are much too tight, which makes it hard to slide in the case
at the back. Will fix in a future revision.

### [Samla Box clips](Ender-3%20Mechanical/Ender-3%20Upgrades/Samla%20Box%20clips)

These are box clips for the [IKEA SAMLA series](https://www.ikea.com/us/en/cat/samla-series-12553/)
of storage boxes. I intended to use these to make a filament drybox, but I have not gotten around to
completing that project.

### [X Carriage](Ender-3%20Mechanical/Ender-3%20Upgrades/X%20Carriage)

This is my biggest and most important upgrade. This upgrade is complete and is currently in use on
the current iteration of my Ender 3 Pro. This is a completely redesigned x-axis carriage that scraps
all the stock hot-end parts except for the metal plate and the three rollers. Features include:

* Direct Drive
* E3D V6 support
* Can use 30mm hotend cooling fan and fan duct included with the V6
* Can use a 4010 (or 4020) hotend cooling fan with a fan duct adapter
* Custom extruder with Bondtech dual drive gear support
* 5015 part cooling fan and fan duct

My design takes heavy inspiration from the Prusa i3 x-axis carriage design. 

### [Raspberry Pi 3 Model B](Ender-3%20Mechanical/Ender-3%20Upgrades/raspberry-pi-3-model-b-reference-design-solidworks-cad-rpi-raspberrypi-raspberry-pi-1.snapshot.83)

This is just a model of the Raspberry Pi 3 Model B that I use to run Octoprint and Klipper.


## Software upgrades

The software modifications I made are not included in this directory. The main change I made was 
installing [Klipper](https://www.klipper3d.org/) instead of Marlin for the firmware and having it 
run via Octoprint. I use PrusaSlicer as my slicer, although I have had good experience with Ultimaker
Cura and would recommend that as well (I used that originally). 


