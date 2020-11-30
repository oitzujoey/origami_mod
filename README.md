
# README.md

## Config

| Type | Cvar | VM | Default | Description |
|-|-|-|:-:|-|
| bool | g_rampjump | Server, Client | 0 | Allow accumulative jumps. |
| bool | g_stepsmoothing | Server, Client | 0 | Make accent up stairs easier. |
| bool | g_upstep | Server, Client | 0 | Allow stepping when velocity is positive. It is recommended to enable g_stepsmoothing as well to prevent strange side-effects. |
| bool | g_autojump | Server, Client | 0 | Jump does not have to be released to jump again. |

| Command | Effect |
|-|-|
| dropweapon | Drop the current weapon you are carrying. |
| dropammo | Drop one full set of ammo of the weapon you are carrying if able. |
| +crouch | Alternative crouch. Allows jumping while crouched. |

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

g_airacclerate and g_strafeaccelerate do not take the same values for acceleration. For CPM movement this doesn't matter since only g_strafeaccelerate is used, but if you want to use QuakeWorld accel values, it won't work as expected. This is because g_strafeaccelerate is based upon the CPM air acceleration model, and g_airaccelerate is based off of the QW model. Fortunately, the g_airaccelerate can be converted to the g_strafeaccelerate model by multiplying by 320/30 or 10.67. Originally I did g_airaccelerate incorrectly, and the QW air acceleration was way too low. This has been fixed to remain consistent with both QW and CPM, which is why this convoluted system is in place.
Air physics has been modified for all modes. High values of g_airacclerate will no longer reduce jump height. I have no idea why that was happening. I think it was a bug in the original code.  
I know that CPM is incorrect. If you have improvements, please tell me. I admit that I used some [code](https://web.archive.org/web/20070214143052/http://games.linuxdude.com/tamaps/archive/cpm1_dev_docs.zip) (It's a zip) that fell under the old Q3A mod license, but I have tried to purge it. This has resulted in a less accurate imitation of CPM physics. At least you have access to the source code as a result.  
Source code is available under GPL v2 at <https://github.com/oitzujoey/origami_mod>. If it is gone, then try looking at <http://www.origamiparade.com>. If that's gone, try <https://www.archive.org>. If that's gone, well... you're probably out of luck, but I'd be amused to know that my mod survived the downfall of civilization.  
