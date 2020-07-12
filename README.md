
# README.md 

## Config

| Type  | Cvar                  | VM     | Default | Description                                                                                       |
|-------|-----------------------|--------|:-------:|---------------------------------------------------------------------------------------------------|
| float | g_doublejump          | Server | 0       | Give a boost if a jump is done within 400 ms of the last one.                                     |
| float | g_aircontrol          | Server | 0       | CPM air control. 5--10 is a good number.                                                          |
| float | g_strafeaccelerate    | Server | 1       | Air acceleration that is only applied when strafing in a CPM-like mode (g_cpmkbd || g_orikbd)     |
| float | g_wishspeed           | Server | 400     | The thing that makes you go slow in Q1                                                            |
| float | g_rampboost           | Server | 0       | Give a boost when jumping up ramps. 100 is a good number.                                         |
| float | g_acclerate           | Server | 10      | pm_accelerate: Ground acceleration                                                                |
| float | g_airacclerate        | Server | 1       | pm_airaccelerate: Air acceleration                                                                |
| float | g_friction            | Server | 6       | pm_friction: Ground friction                                                                      |
| float | g_crouchfriction      | Server | 1       | Reduce (or increase) friction when crouched. This is a factor of g_friction.                      |
| bool  | g_cpmkbd              | Server | 0       | Turn CPM keyboard specific movement rules on or off.                                              |
| bool  | g_orikbd              | Server | 0       | Turn CPM-like keyboard specific movement rules on or off. This is for forward and backward.       |
| float  | g_crouchdrop          | Server | 0      | Press crouch to drop faster. Useful to prevent overshooting the top of ledges when using bounce pads. |
| float | g_lightningdischarge | Server | 0 | Quake lightning gun discharge. |
| bool  | g_backpack            | Server | 0       | Not implemented. Comes from Q1.                                                                   |
| bool  | g_teleportprojectiles | Server | 0       | Not implemented. If you know how to do this, I would appreciate your help.                        |

That's it for now.  
There are several example config files in the physics directory:

| | |
|-|-|
| VQ3: | Pretty accurate implementation if I do say so myself. |
| Q1: | Is supposed to be Q1. Who knows if I got it right. |
| CPM: | Seems pretty close to CPM physics. The air control and a few variables may be off though. |
| Origami Mode: | Rat has its own, so why can't I? Like CPM, but without W air control. Crouching allows you to fall faster and slide. |
| Weird Physics: | Like Origami, but without the A & D wishspeed limitation. It's fast. |

## Notes:
Air physics has been modified for all modes. High values of g_airacclerate will no longer reduce jump height. I have no idea why that was happening. I think it was a bug in the original code.  
I know that CPM is incorrect. If you have improvements, please tell me. I admit that I used some [code](https://web.archive.org/web/20070214143052/http://games.linuxdude.com/tamaps/archive/cpm1_dev_docs.zip) (It's a zip) that fell under the old Q3A mod license, but I have tried to purge it. This has resulted in a less accurate imitation of CPM physics. At least you have access to the source code as a result.  
Source code is available under GPL v2 at <https://github.com/oitzujoey/origami_mod>. If it is gone, then try looking at <http://www.origamiparade.com>. If that's gone, try <https://www.archive.org>. If that's gone, well... you're probably out of luck, but I'd be amused to know that my mod survived the downfall of civilization.  
