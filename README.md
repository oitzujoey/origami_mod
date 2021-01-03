
# README.md

## Config

| Type | Cvar | VM | Default | Description |
|-|-|:-:|:-:|-|
| bool | g_autojump | Server, Client | 0 | Jump does not have to be released to jump again. |
| bool | cg_drawSpeed3D | Client | 0 | cg_drawSpeed, but with vertical velocity added in as well. |
| bool | g_missiletriggers | Server, Client | 0 | Allow projectiles to teleport. |
| int | g_movement | Server, Client | 0 | Select movement rules. |
| bool | g_rampjump | Server, Client | 0 | Allow accumulative jumps. |
| bool | g_stepsmoothing | Server, Client | 0 | Make accent up stairs easier. |

| Command | Effect |
|-|-|
| dropweapon | Drop the current weapon you are carrying. |
| dropammo | Drop one full set of ammo of the weapon you are carrying if able. |
| +crouch | Alternative crouch. Allows jumping while crouched. |

That's it for now.  
There are several example config files in the physics directory:

| g_movement | Ruleset | Description |
|-|-|-|
| 0 | VQ3 | Pretty accurate implementation if I do say so myself. |
| 1 | QW | QuakeWorld. May have issues. |
| 2 | CPM | Seems pretty close to CPM physics. The air control and a few variables may be off though. |
| 3 | Origami Mode | Rat has its own, so why can't I? Like CPM, but without W air control. Crouching allows you to slide. |

## Build

There are two ways to build this mod. The manual way is to run "make", copy the qvm files to the pak directory, and then zip it up. If you are on Windows, this is the only way. On Linux, there is a faster way that uses the "mod.bash" script. Simply run "./mod.bash", and the script will build and make the mod. The mod will then be copied to your OpenArena home directory. If a map name is given as an argument, the script will start OA and load the map with cheats enabled.

## Notes

Air physics has been modified for all modes. High values of g_airacclerate will no longer reduce jump height. I have no idea why that was happening. I think it was a bug in the original code.  
I know that CPM is incorrect. If you have improvements, please tell me. I admit that I used some [code](https://web.archive.org/web/20070214143052/http://games.linuxdude.com/tamaps/archive/cpm1_dev_docs.zip) (It's a zip) that fell under the old Q3A mod license, but I have tried to purge it. This has resulted in a less accurate imitation of CPM physics. At least you have access to the source code as a result.  
Source code is available under GPL v2 at <https://github.com/oitzujoey/origami_mod>. If it is gone, then try looking at <http://www.origamiparade.com>. If that's gone, try <https://www.archive.org>. If that's gone, well... you're probably out of luck, but I'd be amused to know that my mod survived the downfall of civilization.  
