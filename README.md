# [Open Hardware DSP Platform](http://www.ohdsp.org)
## CoreOne-xCORE200
### Revision 2.1

---
# README
### Disclaimer
Copyright Paul Janicki 2019

Licensed under the TAPR Open Hardware License (www.tapr.org/OHL)

This documentation is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A PARTICULAR PURPOSE.

### What is this repository?

**Quick summary**

This is Open Hardware DSP Platform CoreOne-xCORE200 Module Revision 2.0. 

This is a less cramped XMOS 200 based DSP and mirocontroller PCB design with USB, SPDIF, I2S/TDM, SPI, I2C, and Ethernet connectivity options.

This repository contains the KiCad design files, manufacturing Gerber/drill files, PDF/drawing files, and relevant documenation for this board.

**Changelog**
Revision 2.1 has the following changes over Revision 2.0:
Added better grounding on power connector only, added extra vias.

Revision 2.0 has the following changes over Revision 1.0:
The ST1S40 regualtors have been replaced with RT7285C parts
The CS2100 clock generator has been removed
The TPS3808 reset circut has been replaced with an NCP308 part
There are now components on the bottom layer to reduce cramping
Third I2S connector removed
Added second I2C and second SPI connectors


### What is the project folder structure?
Most folder names are self explanatory. Starting from the top level: \
*CoreOne*
+ *Bill of Materials*  - This contains the bill of materials in CVS, LibreOffice Calc and XML formats
+ *Drawings* - This contains PDF and SVG Schematic and PCB files
+ *Gerbers* - This contains the PCB Gerbers and drill drawings for manufacture, there is also a zip file ready to send to most manufacturers
+ *JPEGs* - JPEGs of top and bottom views from 3D viewer
+ *KiCad* - This contains the original KiCad schematic and PCB design files
+ *Pick and Place* - This contains pick and place files for top and bottom sides
### How do I get set up?

**Summary of set up**

1. Set your self up a directory on a local disk, something simple will make life easier (eg C:\Electronics on Windows as used here), but anywhere will do just fine.
2. Download the Kicad-Libs from [https://github.com/ohdsp/KiCad-Libs](https://github.com/ohdsp/KiCad-Libs) and place in C:\Electronics\Kicad-Libs (or your chosen folder) 
3. Create a OHDSP subdirectory in C:\Electronics (so C:\Electronics\OHDSP)
3. Download this project to C:\Electronics\OHDSP\uDSP
4. Fire up Kicad
5. Open the main project file C:\Electronics\OHDSP\uDSP\KiCad\uDSP.pro
7. Do as you wish with the project, just keep it under the TAPR Open Hardware License.
Note: For library issues see below.

Make sure your git setup doesn't exclude files used in the project (like .LIB files) or things may go wrong down the line.


**KiCad Library Configuration**

Note that libraries are setup using relative paths, if you follow the above instructions things should work just fine. Below is the default library setup.

To setup eeschema component libraries:
From KiCad main window go to menu Tools -> Edit Schematic Symbols. In the new Window go to menu Preferences -> Manage Symbol Libraries.

On the new "Symbol Libraries" window select the "Project Specific Libraries" tab. The "Append Library" and "Remove Library" buttons can be used to add/remove enteries.
The standard setup is:

|   | Active | Nickname        | Library Path                                        | Plugin Type | Options | Description |
|---|--------|-----------------|-----------------------------------------------------|-------------|---------|-------------|
| 1 | Ticked | power           | ${KICAD_SYMBOL_DIR}/power.lib                       | Legacy      | (blank) | (blank)     |
| 2 | Ticked | MyKiCadLibs-Lib | ${KIPRJMOD}/../../../KiCad-Libs/MyKiCadLibs-Lib.lib | Legacy      | (blank) | (blank)     |

${KICAD_SYMBOL_DIR}  is set under the Enviromnet Variable Configuration. Close Symbol Libraries dialogue and go "Preferences" -> "Configure Paths..."

${KICAD_SYMBOL_DIR} is set to C:\Program Files\KiCad\share\kicad\library - this is the default for a KiCad install on the C drive

${KIPRJMOD} is automatically set to the location of the project (.pro file), in this example this would be C:\Electronics\OHDSP\uDSP\KiCad


To setup Pcbnew libraries:
From KiCad main window go to menu Tools -> Edit PCB Footprints. In the new Window go to menu Preferences -> Manage Symbol Libraries.

On the new "Symbol Libraries" window select the "Project Specific Libraries" tab. The "Append Library" and "Remove Library" buttons can be used to add/remove enteries.
The standard setup is:

|   | Active | Nickname               | Library Path                                                  | Plugin Type | Options | Description |
|---|--------|------------------------|---------------------------------------------------------------|-------------|---------|-------------|
| 1 | Ticked | MyKiCadLibs-Footprints | ${KIPRJMOD}/../../../KiCad-Libs/MyKiCadLibs-Footprints.pretty | KiCad       | (blank) | (blank)     |

${KIPRJMOD} is automatically set to the location of the project (.pro file), in this example this would be C:\Electronics\OHDSP\uDSP\KiCad


