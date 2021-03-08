# Longer3dPrinterLK4
Settings for the Longer 3D Printer to be used with Octoprint

- Printer is Longer LK4 (non-pro)


#### Quality:
- Layer Height (mm): 0.2
- Shell Thickness (mm): 0.8
- Enable Retraction - On/Yes

#### Fill:
Bottom/Thickness (mm) 1.2
Fill Density (%) 15

#### Speed and Temperature
- Print Speed (mm/s) 65
- Printing Temp (C) 200
- Bed Temperature (C) 60

#### Support
- Support Type : Touching buildplate
- Platform Adhesion: Raft

#### Filament
- Diameter (mm): 1.75
- Flow (%): 100.0


#### Machine
 - Nozzle Size (mm): 0.4

#### Retraction
- Speed (mm/s): 65
- Distance (mm): 6

#### Quality
- Initial Layer Thickness (mm): 0.2
- Initial Layer Line Width (%): 100
- Cut off object bottom (mm): 0.0
- Dual extrusion (mm): 0.15

#### Speed
- Travel Speed (mm/s): 65.0
- Bottom Layer Speed (mm/s): 20
- Infill speed (mm/s): 0.0
- Top/bottom speed (mm/s): 0.0
- Outer shell speed(mm/s): 35.0
- Inner shell speed(mm/s): 35.0

#### Cool
- Minimal layer time (sec) : 5
- Enable cooling fan : Yes/On


#### Machine Settings:
- E-Steps per 1mm filament: 0
- Max width (mm) 220
- Max depth (mm) 220
- Max height (mm) 250
- Extruder Count: 1
- Build area shape: square
- Gcode Flavor: Rep/Rap (Marlin/Sprinter)


#### Start G.Code:

;Sliced at: {day} {date} {time}
;Basic settings: Layer height: {layer_height} Walls: {wall_thickness} Fill: {fill_density}
;Print time: {print_time}
;Filament used: {filament_amount}m {filament_weight}g
;Filament cost: {filament_cost}
;M190 S{print_bed_temperature} ;Uncomment to add your own bed temperature line
;M109 S{print_temperature} ;Uncomment to add your own temperature line
G21        ;metric values
G90        ;absolute positioning
M82        ;set extruder to absolute mode
M107       ;start with the fan off

G28 X0 Y0  ;move X/Y to min endstops
G28 Z0     ;move Z to min endstops

G1 Z15.0 F{travel_speed} ;move the platform down 15mm

G92 E0                  ;zero the extruded length
G1 F200 E3              ;extrude 3mm of feed stock
G92 E0                  ;zero the extruded length again
G1 F{travel_speed}
;Put printing message on LCD screen
M117 Printing...


#### End G.code
;Sliced at: {day} {date} {time}
;Basic settings: Layer height: {layer_height} Walls: {wall_thickness} Fill: {fill_density}
;Print time: {print_time}
;Filament used: {filament_amount}m {filament_weight}g
;Filament cost: {filament_cost}
;M190 S{print_bed_temperature} ;Uncomment to add your own bed temperature line
;M109 S{print_temperature} ;Uncomment to add your own temperature line
G21        ;metric values
G90        ;absolute positioning
M82        ;set extruder to absolute mode
M107       ;start with the fan off

G28 X0 Y0  ;move X/Y to min endstops
G28 Z0     ;move Z to min endstops

G1 Z15.0 F{travel_speed} ;move the platform down 15mm

G92 E0                  ;zero the extruded length
G1 F200 E3              ;extrude 3mm of feed stock
G92 E0                  ;zero the extruded length again
G1 F{travel_speed}
;Put printing message on LCD screen
M117 Printing...
