Place your ZIPped game/program or folder and drag&drop to launch & mount directly loaded content via:

Script `dosbox-run.bat` :
- to run DOSBox shell menu directly or .
- if your "content" have present DOSBOX.BAT file with instructions, they will be executed upon start of your program.
- the script will autoload state on start & autosave state on exit

Executable `dosbox.exe` :
- to simply run original DOSBox shell environment without extra options.

Default hotkeys (via README):
ALT-ENTER     fullscreen on/off
ALT-PAUSE     Pause/Unpause emulation.
CTRL-F1       Start the keymapper.
CTRL-F4       Change between mounted floppy/CD images. Update directory cache 
              for all drives.
CTRL-ALT-F5   Start/Stop avi video capturing
CTRL-F5       Save a PNG screenshot
CTRL-F6       Start/Stop recording WAV sound .
CTRL-ALT-F7   Start/Stop recording of OPL commands DRO.
CTRL-ALT-F8   Start/Stop recording of raw MIDI commands.
CTRL-F7       Decrease frameskip.
CTRL-F8       Increase frameskip.
CTRL-F9       Kill DOSBox.
CTRL-F10      Capture/Release the mouse.
CTRL-F11      Slow down emulation (Decrease DOSBox Cycles).
CTRL-F12      Speed up emulation (Increase DOSBox Cycles)*.
ALT-F12       Unlock speed (turbo button/fast forward)**.
LALT-F5       Save to current slot.
LALT-F9       Load state from current slot.
LALT-F6       Switch to previous slot. (MAX of 10 - slots in circular arrangement).
LALT-F7       Switch to next slot. (MAX of 10 - slots in circular arrangement).
CTRL-ALT-HOME Restart DOSBox.
F11, ALT-F11  (machine=cga) change tint in NTSC output modes***.
F11           (machine=hercules) cycle through amber, green, white colouring***.

*NOTE: Once you increase your DOSBox cycles beyond your computer CPU resources,
       it will produce the same effect as slowing down the emulation.
       This maximum will vary from computer to computer.

**NOTE: You need free CPU resources for this (the more you have, the faster
        it goes), so it won't work at all with cycles=max or a too high amount
        of fixed cycles. You have to keep the keys pressed for it to work!

***NOTE: These keys won't work if you saved a mapper file earlier with
         a different machine type. So either reassign them or reset the mapper.