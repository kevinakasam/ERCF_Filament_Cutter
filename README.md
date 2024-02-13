

 <img src="Images/Banner.png" width=100% >  

# Enraged Rabbit Encoder Cutter - Beta 6.0 🥕
<p align="center">
  <a aria-label="Stars" href=""><img src="https://img.shields.io/github/stars/kevinakasam/ERCF_Filament_Cutter?style=flat-square"></a> &nbsp; 
  <a aria-label="License" href=""><img src="https://img.shields.io/github/license/kevinakasam/ERCF_Filament_Cutter"></a> &nbsp;
  <a aria-label="Commits" href=""><img src="https://img.shields.io/github/commit-activity/y/kevinakasam/ERCF_Filament_Cutter"></a> &nbsp;
</p>



### Attention!
<strong> I’m not an expert and 3D printing is just my hobby. So please be careful when you build this mod and don’t just go ahead. All parts are tested and working. But everybody bears the risks of a modification him/herself! I'm not responsible if any harm occurs, so be careful, especially with the knife! </strong>

## Overview

**[EREC](#erec)**<br>
**[BOM](#bom)**<br>
**[Firmware](#firmware)**<br>
**[Showroom](#user-print-showroom)**<br>
**[Acknowledgements](#acknowledgements)**<br>
**[Changelog](#changelog)**<br>
## EREC

This is a simple filament cutter for the awesome ERCF so tip tuning is less important.

It's made out of a Servo and a scalpell/exacto knife blade. The cutter get's mouted to the selector chart just behind the encoder - the cutter is basically an arm that swings to the left and right. Since the ECAS sits now on the Arm the filament path can be opened by swining the arm to the side. Then the ERCF can feed some filament mid air (*the filament tip*) and when the arm swings back to close the filament path the tip gets cut off by the knife on the arm. The cut off tip just falls off to the ground and the filament can be loaded with a clean tip the next time.

#### Why?
I never thought about a filament cutter untill I saw the [Filametrix](https://github.com/sorted01/Filametrix) design / got it recommended. Since I'm not using the ERCF with a Stealthburner (for now at least) I would have to make a cutter on my own. At the same time u/[BioKeks](https://github.com/BioCookieYT) requested a cutter for my Ender 3 fan duct ([Frankenstein 2.0](https://github.com/kevinakasam/FrankEnstein-Duct/tree/main/Frank2.0_Beta)) and that way I though we need something universial. After some days of tinkering this was the result - first with the MG90s servo, but that was so weak it was far aways from cutting it. So long speech short, thanks to [sorted01](https://github.com/sorted01) for the idea with the cutter!

#### Current Status
Considering my other ongoing [projects](https://kevinakasam.com/), I’ve decided to appoint u/[BioKeks](https://github.com/BioCookieYT) as the new primary contributor to this project. Don’t worry, I’m not completely stepping away, but if you have any questions, feel free to ask u/[BioKeks](https://github.com/BioCookieYT).![](Images/Render.png)



### BOM

| Qty | Part | Description                                                                                                                                                                      
| --- | --- |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1 | [Servo MR996](https://amzn.eu/d/gEQACnZ) | That's just the servo I use, nothing special. But the MG90S are definetly too weak. 60° may work, but I highly recommend getting at least a 90° servo.   Also check the torque, u/[BioKeks](https://github.com/BioCookieYT) was't able to cut soft PLA with a 12kg.cm servo
| 1 | [Exacto knife blade No. 11](https://amzn.eu/d/0ZmUXIy) | That's just an example so you know the shape/type. I didn't test these! A higher quality blade probably last longer.                                                             |
| 1 | 5V buck converter | The Servo can take quite a lot of current, enough to shut down my ERCF board. If you have the same problem try a buck converter wired to the PSU or use your dedicated 5V PSU    |
| ... | ... | I will add more later but it's just some screws, inserts and washers                                                                                                             |



## Firmware
<table>
<tr>
<td width=20%><img src="https://github.com/moggieuk/Happy-Hare/raw/main/doc/happy_hare_logo.jpg" alt='KlipperScreen'></td>
<td>
EREC uses the awesome Happy Hare firmware for the ERCF. I'm sure this also works with the stock macros, but I haven't tried that. In addition, the Happy Hare <code>[mmu_servo]</code> works a lot better than the stock <code>[servo]</code> from Klipper.

<p>

[Macros](Doc/Firmware.md) &nbsp;&nbsp; [Happy Hare](https://github.com/moggieuk/Happy-Hare/blob/main/doc/ercf_v2.md)
</td>
</tr>
</table>

<br>

## Acknowledgements
Thanks to...

* [BioKeks](https://github.com/BioCookieYT) for tinkering with me! Luckily we both got the ERCF roughly at the same time :D

* [xF4m3](https://github.com/xF4m3) for the Macro help!

* [sorted01](https://github.com/sorted01) for the idea with the cutter!

* [moggieuk](https://github.com/moggieuk) for the [awesome firmware](https://github.com/moggieuk/Happy-Hare/tree/23604442613be6bbbc8c70f57ff55fe65b1268e4) and the quick help on the Voron Discord!

And of course thanks to [EtteGit](https://github.com/EtteGit) and the amazing ERCFV2 Team for the awesome [EnragedRabbitProject](https://github.com/EtteGit/EnragedRabbitProject)!

### Showroom 


 <img src="Images/Cutter1.jpg" width=49% >  <img src="Images/Cutter2.jpg" width=49% >

 #### Cutter Action:
 
<a href="http://www.youtube.com/watch?feature=player_embedded&v=-_qIqNOiTIw
" target="_blank"><img src="Images/yt.png" 
alt="Cutter Preview" width="32%" border="10" /></a> 
 






### Changelog

#### 30/09/2023: Binky Support
- Adaption of the Binky encoder for the cutter - made by u/[BioKeks](https://github.com/BioCookieYT)
- Fixed an overhang issue with the `Servo_Mount.stl`

#### 01/10/2023: [Triple-Decky](https://github.com/gneu42/Triple-Decky/tree/main) Support
- Adaption of the Binky encoder for the 3PS version - made by u/[BioKeks](https://github.com/BioCookieYT)

#### 10/10/2023: Bowden Tube Adjustment
- Improved bowden tube fit by adjusting the encoder - Thanks for the feedback u/[xF4m3](https://github.com/xF4m3)  
- Fixed an overhang issue with the `Encoder_Cart_Left.stl` - made by u/[BioKeks](https://github.com/BioCookieYT)

#### 03/11/2023: Beta5 Release
- Overhauled the cutter design for more cutting power and reliability
- Adaption of the Binky encoder for Beta5 - made by u/[BioKeks](https://github.com/BioCookieYT)

#### 23/12/2023: ERCF2.0 Release
- Adaption for the new ERCF2.0 Encoder - made by u/[BioKeks](https://github.com/BioCookieYT)

#### XX/XX/XXXX: Beta6 Release
**NOTE: Beta6 drops support for the old ERCFV1 Encoder**
- XXX