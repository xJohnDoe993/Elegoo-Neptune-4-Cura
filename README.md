# Elegoo-Neptune-4
Move the following files into the folder of your Cura
 - /resources/definitions/elegoo_neptune_4.def.json
 - /resources/extruders/custom_extruder_9.def.json
 - /resources/extruders/custom_extruder_10.def.json

Change your start GCode to

G28 ;home
G92 E0 ;Reset Extruder
G1 Z4.0 F3000 ;Move Z Axis up
G92 E0 ;Reset Extruder
G1 X1.1 Y20 Z0.28 F5000.0 ;Move to start position
G1 X1.1 Y80.0 Z0.28 F1500.0 E10 ;Draw the first line
G1 X1.4 Y80.0 Z0.28 F5000.0 ;Move to side a little
G1 X1.4 Y20 Z0.28 F1500.0 E20 ;Draw the second line
G92 E0 ;Reset Extruder
G1 Z2.0 F3000 ;Move Z Axis up

End Gcode should be fine, here is what should be inside:

G91 ;Relative positionning
G1 E-2 F2700 ;Retract a bit
G1 E-2 Z0.2 F2400 ;Retract and raise Z
G1 X5 Y5 F3000 ;Wipe out
G1 Z10 ;Raise Z more
G90 ;Absolute positionning
G1 X0 Y230 ;Present print
M106 S0 ;Turn-off fan
M104 S0 ;Turn-off hotend
M140 S0 ;Turn-off bed
M84 X Y E ;Disable all steppers but Z"
