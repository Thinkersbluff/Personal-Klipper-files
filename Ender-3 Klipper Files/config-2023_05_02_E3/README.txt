This configuration captured from MAINSAIL OS on my pi3b+ on 2 May 2023.

New at this version:
- Activated exclude_object
- Implemented three macros: M300, Load Filament and Unload Filament

Cura 5.2.2 already labels the objects
Moonraker configured to convert the code for Klipper to manage object exclusion

NOTE: Apparently, Cura treats support as its own entity, so even if the object is excluded, Klipper will continue trying to print supports (so basically don't try to exclude objects if they are being printed with support.)