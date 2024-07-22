

 <img src="Images/Banner.png" width=100% >  

# Enraged Rabbit Encoder Cutter - Beta 7.0 🥕
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
**[Assembly](#assembly)**<br>
**[Firmware](#firmware)**<br>
**[Changelog](#changelog)**<br>
**[Showroom](#user-print-showroom)**<br>
**[Acknowledgements](#acknowledgements)**<br>

## EREC

This is a simple filament cutter for the awesome ERCF so tip tuning is less important.

It's made out of a Servo and a scalpell/exacto knife blade. The cutter get's mouted to the selector chart just behind the encoder - the cutter is basically an arm that swings to the left and right. Since the ECAS sits now on the Arm the filament path can be opened by swining the arm to the side. Then the ERCF can feed some filament mid air (*the filament tip*) and when the arm swings back to close the filament path the tip gets cut off by the knife on the arm. The cut off tip just falls off to the ground and the filament can be loaded with a clean tip the next time.

#### Why?
I never thought about a filament cutter untill I saw the [Filametrix](https://github.com/sorted01/Filametrix) design / got it recommended. Since I'm not using the ERCF with a Stealthburner (for now at least) I would have to make a cutter on my own. At the same time u/[BioKeks](https://github.com/BioCookieYT) requested a cutter for my Ender 3 fan duct ([Frankenstein 2.0](https://github.com/kevinakasam/FrankEnstein-Duct/tree/main/Frank2.0_Beta)) and that way I though we need something universial. After some days of tinkering this was the result - first with the MG90s servo, but that was so weak it was far aways from cutting it. So long speech short, thanks to [sorted01](https://github.com/sorted01) for the idea with the cutter!

#### Current Status
Considering my other ongoing [projects](https://kevinakasam.com/), I’ve decided to appoint u/[BioKeks](https://github.com/BioCookieYT) as the new primary contributor to this project. Don’t worry, I’m not completely stepping away, but if you have any questions, feel free to ask u/[BioKeks](https://github.com/BioCookieYT)!
<br>
<br>
<img src="Images/EREC_Beta7.png" width=100%>



## BOM
<table>
<tr>
<td width=25%><img src="Images/EREC_Hardware.png" alt='KlipperScreen'></td>
<td>
You can find the EREC BOM here. Make sure to gather all the required hardware before starting the assembly process ;)
<p>

[BOM](Doc/Firmware.md) 
</td>
</tr>
</table>

<br>

## Assembly 

<table>
<tr>
<td>
The assembly process is straightforward; I’ve tried my best to keep it simple. If you need any help, feel free to join our discord server. 
<p>

[Documentation](Doc/EREC_Assembly.pdf) &nbsp;&nbsp; [Discord Server](https://discord.gg/Jw4frr64yV) &nbsp;&nbsp; [Discord Channel Link](https://discord.com/channels/964441223169449984/1169733100700434543)
<td width=35%><img src="Images/Assembly.png"></td>
</td>

</tr>
</table>

<br>

## Firmware
<table>
<tr>
<td width=20%><img src="https://github.com/moggieuk/Happy-Hare/wiki/resources/happy_hare_logo.jpg" alt='KlipperScreen'></td>
<td>
EREC uses the awesome Happy Hare firmware for the ERCF. I'm sure this also works with the stock macros, but I haven't tried that. In addition, the Happy Hare <code>[mmu_servo]</code> works a lot better than the stock <code>[servo]</code> from Klipper.

<p>

[Macros](Doc/Firmware.md) &nbsp;&nbsp; [Happy Hare](https://github.com/moggieuk/Happy-Hare/blob/main/doc/ercf_v2.md)
</td>
</tr>
</table>

<br>


## Changelog & Archive 

<table>
<tr>
<td>
EREC has undergone a long development process. Feel free to visit older revisions if you wish to explore its history 🥕
<p>

[Changelog](Doc/EREC_Assembly.pdf) &nbsp;&nbsp; [Archive](https://discord.gg/Jw4frr64yV) 
<td width=25%><img src="Images/Cutter2.jpg"></td>
</td>

</tr>
</table>

<br>




## Showroom
 <img src="Images/Cutter1.jpg" width=49% >  <img src="Images/Cutter2.jpg" width=49% >

 #### Cutter Action:
 
<a href="http://www.youtube.com/watch?feature=player_embedded&v=-_qIqNOiTIw
" target="_blank"><img src="Images/yt.png" 
alt="Cutter Preview" width="32%" border="10" /></a> 


## Acknowledgements
Thanks to...

* [BioKeks](https://github.com/BioCookieYT) for tinkering with me! Luckily we both got the ERCF roughly at the same time :D

* [xF4m3](https://github.com/xF4m3) for the Macro help!

* [sorted01](https://github.com/sorted01) for the idea with the cutter!

* [moggieuk](https://github.com/moggieuk) for the [awesome firmware](https://github.com/moggieuk/Happy-Hare/tree/23604442613be6bbbc8c70f57ff55fe65b1268e4) and the quick help on the Voron Discord!

And of course thanks to [EtteGit](https://github.com/EtteGit) and the amazing ERCFV2 Team for the awesome [EnragedRabbitProject](https://github.com/EtteGit/EnragedRabbitProject)!
