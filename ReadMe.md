# Idle Champions EGS

**Warning**: This script reads system memory. I do not know CNE's stance on
reading system memory used by the game, so use at your own risk. Pointers may
break on any given update and I may no longer decide to update them.

This repository and scripts therein are specifically tailored to Idle Champions
ran through the Epic Games Store. These scripts will not work without
modification for other platforms and their specific memory pointers.

## Instructions for `ModronGUI.ahk`

1. Download and install AutoHotkey: https://www.autohotkey.com/
2. Download `ModronGUI.ahk`, `IC_MemoryFunctions.ahk`,
`IC_ServerCallFunctions.ahk`, `json.ahk`, and `classMemory.ahk` to the same
folder.
3. Scan all downloaded files with trusted antivirus software.
4. Right click `ModronGUI.ahk` and select run script.
5. Read and follow the instructions on the `Read First` tab.
6. In the in game settings, uncheck `Disable F1-F12 Leveling` if it is checked.

Recommended additional steps:

* Review AutoHotkey tutorials and documentation.

Notes:

1. Script requires Shandie, Briv and Modron Automation.

## Settings Documentation

### Seats to level with Fkeys

Check the boxes for each seat you want the script to level up with Fkey inputs.

### Use Fkey leveling while below this zone

Once the script reads that it has passed the zone number entered here, it will
no longer attempt to level up champions with Fkey inputs.

### Farm SB stacks AFTER this zone

The script will attempt to farm Steelbones stacks once it reads that it has
passed the zone number entered here. At a minimum, this zone should be high
enough that the "W" formation does not kill anything. At a maximum, this zone
should be 5 zones below the Modron reset zone for single skip, 7 zones below
for double skip, 9 zones below for triple skip, and 11 zones below for
quadruple skip.

### Minimum zone Briv can farm SB Stacks on

This is the minimum zone number that your "W" formation can farm Steelbones
stacks. This is only used when 'Enable manual resets to recover from failed
Briv Stacking' is checked.

### Target Haste stacks for next run

When farming Steelbones stacks, the script will attempt to farm enough to have
this amount of Haste stacks for the next run. You will have to calculate how
many Haste stacks you need to complete your gem farm runs.

### Maximum time (ms) script will spend farming SB stacks

When the script is set to farm Steelbones stacks online it will do so until
enough stacks are farmed to satisfy the 'Target Haste stacks for next run' or
this much time in milliseconds has passed, which ever happens first. Note the
script may try and farm more stacks if this time passes and it has not
satisfied the 'Target haste stacks for next run' setting.

### Maximum time (ms) script will wait for Dash (0 disables)

With a high enough ilvl Melf or Hew it can be faster to idle on zone one until
Shandie's Dash ability activates. The script will attempt to detect this on its
own, but if more than the amount of time passes input here (in milliseconds)
then it will proceed. Note, the time here is modified based on the in game time
scale multiplier when potions are used. Entering 0 (zero) will disable waiting
on zone one until Shandie's Dash ability activates.

### Hew's ultimate key (0 disables)

The script will attempt to continously use Hew's ultimate by inputting this
value to the game client. Entering 0 (zero) will disable this function. It is
recommended that if you enable this function and use Havilar with Dembo
summoned that you remove her from the "E" formation so as to not accidentally
unsommon Dembo.

### Use ults 2-9 after initial champion leveling

On zone one after waiting for Dash to activate or in the case of disabling Dash
wait after completing zone one, the script will spend two seconds repeatedly
inputing 2 through 9 to summon Dembo when this box is checked.

### Swap to 'e' formation to cancel Briv's jump animation

When checked, this box enables a function that will attempt to swap out Briv
when a zone is completed and then swap him back in before the next zone is
fully loaded. This eliminates most of his jump animation most of the time
saving a significant amount time. Enabling this function is highly recomended.

### Briv swap sleep time (ms)

When 'Swap to 'e' formation to cancel Briv's jump animation' is enabled, you
may need to adjust this value to maximize the functions efficiency. If you see
Briv's landing animation then this value should be made larger. If Briv is not
being put back in the formation until after monsters spawn then this value
should be made smaller. 2000 is the recomended starting point, but you should
expect to tweak. This value may need to be tweaked again if you use different
combinations of potions.

### Swap to 'e' formation when on boss zones

This function will remove Briv when the script reads that it has landed on a
boss zone. This is only recomended for high quadruple skip Briv's who can end
up on boss zones.

### Uncheck if using a familiar on click damage

When this box is checked, the script will input '\`' key to level up click
damage, requiring one less familiar on gem runs.

### Enable manual resets to recover from failed Briv stacking

When this box is checked, Briv has less than 50 Haste stacks, and the script
reads a zone higher than 'Minimum zone Briv can farm SB stacks on' then the
script will attempt to farm Steelbones stacks, manually end the adventure by
inputting 'r' and then clicking complete (taking control of the mouse), close
the game client, make a server call to load the adventure you started in, open
the game client, and start a new run with enough Haste stacks for a standard
run.

### Enable manual resets to recover from failed Briv stack conversion

When this box is checked, on zone one the script will check if Briv Haste stack
count is less than 'Target Haste stacks for next run' while the Steelbone stack
count is greater than 'Target Haste stacks for next run', indicating that the
Modron Reset did not convert the farmed Steelbones stacks to haste, a rare bug.
When this scenario is true, the script will attempt to manually end the
adventure by inputting 'r' and then clicking complete (taking control of the
mouse), close the game client, make a server call to load the adventure you
started in, open the game client, and start a new run with enough Haste stacks
for a standard run.

### Have Script check for Modron reset Level

In rare cases, Briv's combined Steelbone and Haste stack can fall below the
'Target Haste stacks for next run' immediately after what would be Briv's final
jump before a Modron Reset, resulting in the script entering the Steelbones
stack farming functions while the game client then immediately triggers a
Modron reset. By knowing the Modron reset level, the script can avoid this
scenario. For some users, the script cannot accurately read the Modron reset
level and would require a message box input at the begining of each script
start up, those users may want to consider unchecking this box.

### Change Install Path

The script will attempt to restart the game client when it crashes, to farm
Briv Steelbones stacks, and recover from various scenarios where stacks are
not farmed or converted correctly, if those functions are enabled. The script
will need to know the correct install path for the game client to do so.

---

CHEST BUYTING AND OPENING RELATED SETTINGS DOCUMENTATION COMING SOON.
