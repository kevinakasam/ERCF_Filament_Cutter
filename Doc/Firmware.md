# Firmware 🥕

I'm using the awesome [Happy Hare](https://github.com/moggieuk/Happy-Hare) firmware for the ERCF. I'm sure this also works with the stock macros, but I haven't tried that. In addition, the Happy Hare `[mmu_servo]` works a lot better than the stock `[servo]` from Klipper.

#### Changes to mmu_software.cfg

If the `[gcode_macro _MMU_POST_UNLOAD]` section isnt yet defined in your `mmu_sotware.cfg` simply copy the whole following block into the file (there's already a section with un-loading macros). If it's already there just paste the `CUTTER_ACTION` Macro there

```
# Callback macros for modifying Happy Hare behavour
# This occurs after unloading filament on a toolchange
#
# This can be used for the Filament Cutter
# Note that restoration to original toolhead position is ensured by Happy Hare.
#
[gcode_macro _MMU_POST_UNLOAD]
description: Optional post unload routine for filament change
gcode:
    CUTTER_ACTION
```

#### Cutter config

Add this to your config. I added a file named `mmu_ercf_cutter.cfg` in the ` /config/mmu/optional` to implement it with a `[include mmu/optional/mmu_ercf_cutter.cfg]`.
Note: The Macros aren't done yet ~~and aren't working as expected~~.

```
[mmu_servo cut_servo]         #`mmu_servo` only for the Happy Hare firmware, otherwise only `servo`
pin: mmu:PA7                  #Extra Pin on the ERCF easy Board
maximum_servo_angle: 180      #Set this to 60 for a 60° Servo
minimum_pulse_width: 0.0005   #Adapt these for your servo
maximum_pulse_width: 0.0025   #Adapt these for your servo

[gcode_macro _CUT_VAR]
description: Empty macro to store the variables

### Servo ###
variable_servo_closed_angle: 70          #Adapt these for your setup
variable_servo_open_angle: 10            #Adapt these for your setup
variable_servo_blocked_angle: 40         #I have the idea to home the filament against the cutter by blocking the filament path with 1/2 of the servo rotation. Could make cuts more precise
variable_servo_idle_time: 500            #Time to let the servo reach it's position, in milliseconds (1 second = 1000 milliseconds)

### Feed length
variable_feed_length: 48                 #Rough estimation of the parking position to the outside of the encoder
variable_cut_length: 10                  #How much you want to cut off in mm
variable_cut_amount: 1                   #Number of times the cutter tries to cut the filament

gcode:


[gcode_macro CUTTER_CLOSE]
description: Set Servo in the close position
gcode:
    {% set cutvar = printer["gcode_macro _CUT_VAR"] %}
    SET_SERVO SERVO=cut_servo ANGLE={cutvar.servo_closed_angle}
    SET_SERVO SERVO=cut_servo WIDTH=0.0
    G4 P{cutvar.servo_idle_time}
    M118 Cutter closed
    M400
    G4 P0

[gcode_macro CUTTER_OPEN]
description: Set Servo in the open position
gcode:
    {% set cutvar = printer["gcode_macro _CUT_VAR"] %}
    SET_SERVO SERVO=cut_servo ANGLE={cutvar.servo_open_angle}
    SET_SERVO SERVO=cut_servo WIDTH=0.0
    G4 P{cutvar.servo_idle_time}
    M118 Cutter open
    M400
    G4 P0

[gcode_macro CUTTER_BLOCK]
description: Set Servo in the blocked position
gcode:
    {% set cutvar = printer["gcode_macro _CUT_VAR"] %}
    SET_SERVO SERVO=cut_servo ANGLE={cutvar.servo_blocked_angle}
    SET_SERVO SERVO=cut_servo WIDTH=0.0
    G4 P{cutvar.servo_idle_time}
    M118 Cutter blocked
    M400
    G4 P0

# New Cutter Action Macro - thanks to xF4m3 and moggieuk <3
[gcode_macro CUTTER_Action]
description: Set Servo in the close position. Doesn't work properly yet.
gcode:
    {% set cutvar = printer["gcode_macro _CUT_VAR"] %}
    
    CUTTER_OPEN
    MMU_TEST_MOVE MOVE={cutvar.feed_length + cutvar.cut_length}
    {% for i in range(cutvar.cut_amount) %}
      CUTTER_CLOSE
      CUTTER_OPEN
    {% endfor %}
    MMU_TEST_MOVE MOVE=-1
    CUTTER_CLOSE
    
   _MMU_STEP_SET_FILAMENT STATE=1 
   _MMU_STEP_UNLOAD_GATE
   
    M400
    G4 P0
   


## Old Cutter Action Macro
#[gcode_macro CUTTER_Action]
#description: Set Servo in the close position. Doesn't work properly yet.
#gcode:
#    {% set cutvar = printer["gcode_macro _CUT_VAR"] %}
#
#    MMU_SERVO POS=down
#    CUTTER_OPEN
#    MMU_TEST_MOVE MOVE={44 + cutvar.cut_length} #Rough estimation of the parking position to the outout of the encoder + the cut length
#    CUTTER_CLOSE
#    CUTTER_OPEN
#    CUTTER_CLOSE
#    CUTTER_OPEN
#    MMU_TEST_MOVE MOVE=-1
#    CUTTER_CLOSE
#    MMU_EJECT
#    #MMU_SERVO POS=down
#    M400
#    G4 P0
```