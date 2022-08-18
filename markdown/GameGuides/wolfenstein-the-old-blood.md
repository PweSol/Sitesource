![Wolfesntein: The Old Blood Guide](Images\wtob_header.png "Shot by Antic Owl"){.shadowed .autosize}

## Summary

Feature | Supported
--|--
Vanilla Photo Mode 		| No
Hotsampling 			| Yes (SRWE)
DSR 					| Yes (Desktop DSR)
Custom Aspect Ratios 	| Yes
Reshade 				| Yes 
Ansel 					| No
Graphics API 			| OpenGL
Game version 			| 0.1464
 
## Tools

* [CE Table by K-Putt and Jim2point0 merged with Sunbeam console unlocker](https://patreon.com/Otis_Inf)  
**Features**: Camera control, tilt, unrestrict CVars and console commands.

## Setup the game
First you will need to check if you can access the ingame console once you have started the game and hooked the CT to his process.
To test it press the ~ key on your keyboard. If it doesn't, add `+com_allowConsole 1` as a launch option via Steam then try again. This should do it.
Be sure to activate the options depicted in the following print screen. Without that, some of the commands in the next section of the guide are not going to be applied.

(Images\cheattable_wolftob.png "Cheat Table Options"){.shadowed .autosize}

**Note about console key**
The console can be also opened via `CTRL+~` even if `Patch the ConsoleKey to Tilde (~)` wasn't checked.

## Making a custom config
To ease the game tweaking, we are going to make a custom configuration that can be executed at each start of the game.
Depending on your hardware, especially CPU and GPU, you will have to modify some of the variables in the commands below.
Save the commands in a new file that you could by example call WolfCustomCfg.cfg in `\steamapps\common\Wolfenstein The Old Blood\base` or `C:\Users\<UserName>\Saved Games\MachineGames\Wolfenstein The Old Blood\base`

```r_dimShadowHeightTweak 0
win_pauseOnAltTab 0
win_allowAltTab 1
r_useSMP 1
r_useHardwareTextures 1
vt_cudaRLE
vt_cudaBudget 8
vt_useCudaTranscode 2
vt_minMipLevelInstalled 16
vt_uncompressedVmtr 0
image_useCompression 0
vt_maxPPF 64
vt_maxaniso 4
image_anisotropy 16
vt_minlod 0
vt_lodBias -2
image_lodbias -2
vt_qualityDCTChroma 100
vt_qualityDCTLuma 100
vt_qualityDCTNormal 100
vt_qualityDCTPower 100
vt_qualityDCTSpecular 100
vt_qualityHDPLossless 1
vt_qualityHDPDiffuse 0
vt_qualityHDPNormal 0
vt_qualityHDPPower 0
vt_qualityHDPSpecular 0
vt_pageimagesizevmtr 16384
vt_pageimagesizeunique 16384
vt_pageimagesizeuniquediffuseonly 16384
vt_pageimagesizeuniquediffuseonly2 16384
vt_useCudaTranscode 2
r_swapInterval 1
vt_restart```

To apply this configuration, open the in-game console and type `exec [yourconfigname.cfg]` 

**Notes about the commands above**
*The commands starting with `vt_pageimagesize` increase the texture data stored in the VRAM. If you have 4GB or less, 8192 is recommended. Changing the `vt_pageimagesizevmtr` above 16384 could lead to a game crash.
*For CPU's with 2 and 4 core without HT the `vt_maxPPF` should be set to 8. For CPU above 4 cores and those with HT you can go up to 64 or 128.Valid settings are: 8, 16, 32, 64 and 128.
*Any change made to a `vt_` variable require a restart.

Some default commands are already available, but are not working as intended. 
Add this set of keybinds to a file called `keybinds.cfg` in your game directory.
By doing `exec keybinds.cfg` via the console, they will be permanently written to the correct file and postion. You will need to do this just once.

```bind "F1" "toggle g_showhud;toggle hands_show"
bind "F2" "toggle ai_enable"
bind "F3" "timescale 0.2"
bind "F4" "timescale 1"
bind "F6" "toggle g_freecam"
bind "F7" "cvarRandom g_stopTime 1 1"
bind "F8" "cvarRandom g_stopTime 0 0"
bind "KP_ADD" "cvaradd g_fov 1, "
bind "KP_MINUS" "cvaradd g_fov -1"
bind "F12" "devgui 1"```

**Note about the free camera and keybinds**
The free camera allows you to move without moving the player from his initial position.
FOV and tilt are not available in this mode. Only forward, backward, left and right. Camera lift up and down are also available.

## Controls 

Key	| Command
--|--
`Num 0` | Toggle camera
`Num 8` / `Num 5` | Move camera forward / backward
`Num 4` / `Num 6` | Move camera left / right
`Num 3` / `Num 9` | Move camera up / down
`[` / `]` | Tilt camera left / right
`ALT` | Fast camera movements
`CTRL+ALT` | Faster camera movements (not available in tilt)
`F1` | Disable/enable HUD and hands 
`F2` | Disable/enable enemies movements
`F3` | Slowmo to 0.2 game speed
`F4` | Normal game speed
`F6` | Enable/disable the internal free camera
`F7` | Stop the game
`F8` | Enable the game back
`NumPad Plus` | Increase FOV by 1
`NumPaD Minus` | Decrease FOV by 1
`F12` | Activate the developper GUI

## Tips and Tricks
It is possible to advance frame per frame when in full time stop.
For this, press the keybind that stop the game and press f12 to enter the devgui.
If you are using an Xbox controller, press D-Pad down and go to Time Control.
Press D-Pad right and then Advance Time One Frame When Stopped. 
You can also map the command `g_runframes 1` to an available key on your keyboard.

Removing the post processing via `r_skippostprocess 1` will also disable the in game DOF.
This can give you a better image quality.

Bind a key to execute your custom configuration. This will avoid having to type the command each time you start the game.

## Useful Links

* [PC Gaming Wiki](https://www.pcgamingwiki.com/wiki/Wolfenstein:_The_Old_Blood)