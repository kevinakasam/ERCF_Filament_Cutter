
# EREC - Changelog 🥕

### 30/09/2023: Binky Support

- Adaption of the Binky encoder for the cutter - made by u/[BioKeks](https://github.com/BioCookieYT)
- Fixed an overhang issue with the `Servo_Mount.stl`
___
### 01/10/2023: [Triple-Decky](https://github.com/gneu42/Triple-Decky/tree/main) Support
- Adaption of the Binky encoder for the 3PS version - made by u/[BioKeks](https://github.com/BioCookieYT)
___
### 10/10/2023: Bowden Tube Adjustment
- Improved bowden tube fit by adjusting the encoder - Thanks for the feedback u/[xF4m3](https://github.com/xF4m3)
- Fixed an overhang issue with the `Encoder_Cart_Left.stl` - made by u/[BioKeks](https://github.com/BioCookieYT)
___
### 03/11/2023: Beta5 Release
- Overhauled the cutter design for more cutting power and reliability
- Adaption of the Binky encoder for Beta5 - made by u/[BioKeks](https://github.com/BioCookieYT)
___
### 23/12/2023: ERCF2.0 Release
- Adaption for the new ERCF2.0 Encoder - made by u/[BioKeks](https://github.com/BioCookieYT)
___
### 12/03/2024: New primary contributor 🥕 
- Considering my other ongoing [projects](https://kevinakasam.com/), I’ve decided to appoint u/[BioKeks](https://github.com/BioCookieYT) as the new primary contributor to this project.
___ 
### 15/02/2024: Beta6 Release 🥕
**NOTE: Beta6 drops support for the old ERCFV1**
- Helical gearing with a higher module to prevent slipping
  From my testing the gears work a lot better then the Beta 5 ones, had not a single slip during my testing
- Moved servo a bit up to fix issue #8
  The new ERCFV2 Encoder changed a bit compared to the original Binky, this required a repositioning of the gears.
- Added lock nut to the pivot to prevent the screw to be loosened over time
- Made whole construction stronger to prevent flexing
- Improved knife mounting
  I'm still not sure about this one, feel free to give your honest opinion about this https://github.com/kevinakasam/ERCF_Filament_Cutter/issues/6
- Made transition between encoder and arm smoother
- Adjusted mounting to be rotated up to 100 degree when loosened
- Improved ECAS mount
- Moved heated insert of encoder 4.5a slightly inward to prevent breaking
- Added some washers
- Added carrot 🥕
- New Logo
___
### 15/02/2024: Beta7 Release 🥕 
**NOTE: Beta7 drops support for 90 degree servos!** <br>
During testing I found out that a 4:1 gear ratio is the best balance between gear size and cutting performance. Older versions of EREC had a 2:1 gear ratio which still was too weak for some special filaments ;)

- New double-helical gearing system to prevent vertical flexing during cutting moves
- New 4:1 gear ratio for even more cutting power
- M3 Heat-set insert to hold filament better in place 
- Stiffer servo mounting to prevent flexing 
- Encoder rail to support `Cutter_Arm` during cutting 
- New mounting for the `Servo_Gear.stl`
- Even more improved knife mounting 
- Angled knife for better cutting performance 
- Support for PC4-M10 bowden couplings 
- Added filament guide to prevent cut pieces from scattering
- Added zip tie holes for better wiring 
- Overhauled documentation for easier assembly
