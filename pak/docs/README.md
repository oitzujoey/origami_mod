
# README.md

## Config

| Type | Cvar | VM | Default | Description |
|-|-|-|:-:|-|
| float | g_acclerate | Server, Client | 10 | pm_accelerate: Ground acceleration |
| float | g_airacclerate | Server, Client | 1 | pm_airaccelerate: Air acceleration |
| float | g_strafeaccelerate | Server, Client | 1 | Air acceleration that is only applied when strafing in a CPM-like mode (g_cpmkbd || g_orikbd) |
| float | g_slickaccelerate | Server, Client | 10 | Acceleration on slick surfaces. |
| float | g_wishspeed | Server, Client | 400 | The thing that makes you go slow in Q1 |
| float | g_strafewishspeed | Server, Client | 30 | The thing that makes you go slow sideways in CPM |
| float | g_aircontrol | Server, Client | 0 | CPM air control. 5--10 is a good number. |
| bool | g_cpmkbd | Server, Client | 0 | Turn CPM keyboard specific movement rules on or off. |
| bool | g_orikbd | Server, Client | 0 | Turn CPM-like keyboard specific movement rules on or off. This is for forward and backward. |
| float | g_friction | Server, Client | 6 | pm_friction: Ground friction |
| float | g_crouchfriction | Server, Client | 1 | Reduce (or increase) friction when crouched. This is a factor of g_friction. |
| bool | g_rampjump | Server, Client | 0 | Allow accumulative jumps. |
| bool | g_quakeramp | Server, Client | 0 | Use Quake ramp physics. |
| float | g_doublejump | Server, Client | 0 | Give a boost if a jump is done within 400 ms of the last one. |
| bool | g_stepsmoothing | Server, Client | 0 | Make accent up stairs easier. Comes at the cost that speed is not increased or decreased when jumping on ramps. |
| float | g_crouchdrop | Server, Client | 0 | Press crouch to drop faster. Useful to prevent overshooting the top of ledges when using bounce pads. |
| float | g_lightningdischarge | Server, Client | 0 | Quake lightning gun discharge. |
| bool | g_backpack | Server, Client | 0 | Not implemented. Comes from Q1.|
| bool | g_teleportprojectiles | Server, Client | 0 | Not implemented. If you know how to do this, I would appreciate your help. |

| Command | Effect |
|-|-|
| dropweapon | Drop the current weapon you are carrying. |
| dropammo | Drop one full set of ammo of the weapon you are carrying if able. |

That's it for now.  
There are several example config files in the physics directory:

| | |
|-|-|
| VQ3: | Pretty accurate implementation if I do say so myself. |
| QW: | Is supposed to be QW. Who knows if I got it right. |
| CPM: | Seems pretty close to CPM physics. The air control and a few variables may be off though. |
| Origami Mode: | Rat has its own, so why can't I? Like CPM, but without W air control. Crouching allows you to fall faster and slide. |
| Weird Physics: | Like Origami, but without the A & D wishspeed limitation. It's fast. |

## Build

There are two ways to build this mod. The manual way is to run "make", copy the qvm files to the pak directory, and then zip it up. If you are on Windows, this is the only way. On Linux, there is a faster way that uses the "mod.bash" script. Simply run "./mod.bash", and the script will build and make the mod. The mod will then be copied to your OpenArena home directory. If a map name is given as an argument, the script will start OA and load the map with cheats enabled.

## Notes

g_airacclerate and g_strafeaccelerate do not take the same values for acceleration. For CPM movement this doesn't matter since only g_strafeaccelerate is used, but if you want to use QuakeWorld accel values, it won't work as expected. This is because g_strafeaccelerate is based upon the CPM air acceleration model, and g_airaccelerate is based off of the QW model. Fortunately, the g_airaccelerate can be converted to the g_strafeaccelerate model by multiplying by 320/3 or 10.67. Originally I did g_airaccelerate incorrectly, and the QW air acceleration was way too low. This has been fixed to remain consistent with both QW and CPM, which is why this convoluted system is in place.
Air physics has been modified for all modes. High values of g_airacclerate will no longer reduce jump height. I have no idea why that was happening. I think it was a bug in the original code.  
I know that CPM is incorrect. If you have improvements, please tell me. I admit that I used some [code](https://web.archive.org/web/20070214143052/http://games.linuxdude.com/tamaps/archive/cpm1_dev_docs.zip) (It's a zip) that fell under the old Q3A mod license, but I have tried to purge it. This has resulted in a less accurate imitation of CPM physics. At least you have access to the source code as a result.  
Source code is available under GPL v2 at <https://github.com/oitzujoey/origami_mod>. If it is gone, then try looking at <http://www.origamiparade.com>. If that's gone, try <https://www.archive.org>. If that's gone, well... you're probably out of luck, but I'd be amused to know that my mod survived the downfall of civilization.  
