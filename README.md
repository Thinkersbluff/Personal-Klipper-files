# This repository contains Thinkersbluff's Personal Klipper files

Rather than try to manage my own configuration files separately from those of @K2Van within the one forked version of his repository, I use this repo to document and preserve my own version of the Klipper configuration files, which I create and maintain for use on my CR6-SE and my Ender-3 printers. You are welcome to study/copy/reuse any of these files, if you wish, but please note that these files may contain errors, inefficiencies and poor programming practices. 

I make no warranty whatsoever that these files are suitable for use by others.  I do, however, like to learn and always appreciate constructive feedback. 
Please 
 - open an Issue here if you wish to flag problems or ask questions or 
 - fork the repository and submit a PR, to recommend enhancements.

# The Printers
I own and operate two Creality 3D printers, both of which sometimes run Klipper (and sometimes Marlin)

## Printer 1: Original Ender-3 (modified)

These modifications to my Ender-3 impact my Klipper configuration files:
 - Micro-Swiss direct-drive extruder
 - BTT SKR e3 Turbo motherboard
 - BLTouch
 - 0.9 degree motor on Y-axis
 
 ## Printer 2: Kickstarter CR6-SE
 
 These modifications to my CR6-SE impact my Klipper configuration files:
 - Orbiter v1.5 geared extruder
 - Moons pancake motor on extruder (runs in opposite direction from original stock motor)
 - BTT SKR CR6 v1.0 motherboard
 - 0.9 degree motor on Y-axis
 
 # The Klipper Host mcus

I run Klipper on a Raspberry Pi 3b+ mcu for the Ender 3.
I run Klipper on a Pi4B+ for the CR6-SE. 
Each Pi has 2Gb of RAM.

# My Choices re: Klipper (and Pi) Front-Ends

I have Linux running on a laptop PC dedicated to my 3D Printer "farm".

I use Mainsail/Moonraker on the two Pis and a Google Chrome browser on the laptop, to control each of the two printers, through a WAN connection to the applicable Pi.  Each Pi is configured to use a unique static IP address.  I also use a Cura plug-in to let me connnect Cura directly to either of the two printers, through Moonraker.

I have one 7" HDMI Pi display, connected to the Pi controlling the Ender 3. I use Klipperscreen on that display, if the laptop is not available.  I also have a mouse and bluetooth keyboard paired with that Pi, to allow me to interact with the Pi OS, though I prefer to use PUtTY as my terminal program. 

# My Klipper Configuration Files

The "Code" section of this repository contains the configuration files named below, grouped into separate folders for each of the printers.

## CR6-SE Klipper Configuration Files

I maintain the following configuration files for the CR6, rather than building one large printer.cfg file
- CR6.cfg  contains the macro codes and parameters specific to controlling the CR6-SE printer (e.g. START_PRINT, END_PRINT, RUN_ABL)
- Mainsail.cfg encapsulates the settings specific to my configuration of the Mainsail front-end
- InputShaper.cfg contains the configuration settings derived from Resonance Compensation
- printer.cfg contains the macro codes and parameters specific to the BTT SKR CR6 motherboard (i.e. If I were to change the motherboard, this would be the configuration file to modify or replace). It also includes CR6.cfg, Mainsail.cfg and InputShaper.cfg at runtime.

In addition to the above, I maintain these configuration files for my CR6-SE Klipper installation
- Moonraker.conf encapsulates the settings specific to my configuration of the Moonraker Klipper/Printer communications broker
- Klipperscreen.conf - auto-generated as part of the KlipperScreen setup
- Webcam.txt - here set up to monitor the one USB camera I use with that printer

## Ender-3 Klipper Configuration Files

I use the same logical organization of configuration files as above, for the Ender-3, except that the file named "CR6.cfg" above is here named "MACROS.cfg":
 - MACROS.cfg
 - Mainsail.cfg
 - printer.cfg
 - InputShaper.cfg
 
 In addition to the above, I maintain these configuration files for my Ender-3 Klipper installation
- Moonraker.conf encapsulates the settings specific to my configuration of the Moonraker Klipper/Printer communications broker
- Webcam.txt - NOT yet set up to monitor the one Pi camera I will use with that printer
- I do not use KlipperScreen with the Ender-3, since I only own one Pi HDMI screen.

If ever I decide to change the configuration of either printer, I will revisit and update this README and the Code section, accordingly.
