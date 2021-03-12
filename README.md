# JubileeKlipper

Klipper custom firmware for Jubilee with 5 bondtech tools.
Board is a Bigtreetech GTR with m5 expansion.
Based on Nanotechs firmware, with a few changes.

-Printer is slightly higher than stock at around 400mm build height.

-Each tool is identical with an added wipe action.

-The tools.cfg defines a retraction length to feed the filament back in after wipe.  This must match settings in prusa slicer for retraction of the tool.*

-Each hotend fan is on a separate controller that auto-magically comes on when hotend is engaged. (may be the same as nanos)

-Parts fans are all hooked to the same control (may be the same as nanos)

-My remote lock is not the standard stepper, so the control macro is a bit different.

-I use a different start gcode to probe the bed and stuff after the bed is hot, but while the hotends heat up.

-More things maybe, I will add if I think of them.

SOON TO COME - Berd-air cooling pump control. Most likely will use poofjuniors selector. https://www.thingiverse.com/thing:3697326
Will update when done.

*The retraction thing is something I ran into when trying the wipe maneuver.  Prusaslicer will retract your retraction length plus your tool change retraction length before going to dock the tool, but it will store the retraction length to put back after change.   

Ex.  retarction length = .6    Tool change retraction length =10  (length of heat chamber) 
Prusa slicer will retract 10.6mm then dock the tool.   After picking up the next tool, it will preform the wipe , but we need to return the retraction to .6 before it gets back because the first thing it will do is de-retract the retraction distance. (.6)     So at the end of the wipe, the tool is set back to the retraction distance that is set in the tools.cfg for the respective tool.  
